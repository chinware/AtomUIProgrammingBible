# 自定义footer

在一些业务场景中，除了常见的确定、取消、打开、关闭、同意、拒绝外，还需要额外的用于处理自定义功能的按钮，`AtomUI` 为这种业务场景提供了 `atom:Dialog.CustomButtons` 与 `atom:MessageBox.CustomButtons` 组件。

在 `AtomUI` 的 `Dialog` 组件中，内置的标准按钮与自定义按钮均被做了角色分类，在 `AtomUI` 中这个角色分类叫做 `Role`，可用为AcceptRole、RejectRole、DestructiveRole、ActionRole、HelpRole、YesRole、NoRole、ApplyRole、ResetRole、CustomRole。这个角色分类涵盖了100%的按钮分类场景。

这个示例中我们通过 `atom:DialogButton` 为开发者演示如何添加一组自定义按钮，如果需要为按钮添加事件，同样通过 `ButtonClicked` 属性进行处理即可。

![AtomUI Dialog组件](./images/custom-footer.webp)

axaml文件：
```axaml
<StackPanel Orientation="Horizontal" Spacing="10">
    <Panel>
        <atom:Button ButtonType="Primary" Name="CustomFooterDialogOpenButton">
            Open Modal
        </atom:Button>
        <atom:Dialog PlacementTarget="CustomFooterDialogOpenButton"
                     IsOpen="{Binding IsCustomFooterDialogOpened, Mode=TwoWay}"
                     Title="Title"
                     IsModal="True"
                     IsLightDismissEnabled="True"
                     StandardButtons="Ok, Cancel"
                     HorizontalStartupLocation="Center"
                     VerticalStartupLocation="Center"
                     DefaultStandardButton="Ok"
                     MinWidth="400">
            <atom:Dialog.CustomButtons>
                <atom:DialogButton Role="ActionRole">Custom Button</atom:DialogButton>
            </atom:Dialog.CustomButtons>
            <StackPanel Spacing="5">
                <TextBlock>Some contents...</TextBlock>
                <TextBlock>Some contents...</TextBlock>
                <TextBlock>Some contents...</TextBlock>
                <TextBlock>Some contents...</TextBlock>
                <TextBlock>Some contents...</TextBlock>
            </StackPanel>
        </atom:Dialog>
    </Panel>

    <Panel>
        <atom:Button ButtonType="Primary" Name="CustomFooterMsgBoxOpenButton">
            Open Modal
        </atom:Button>
        <atom:MessageBox PlacementTarget="CustomFooterMsgBoxOpenButton"
                         IsOpen="{Binding IsCustomFooterMsgBoxOpened, Mode=TwoWay}"
                         Title="Confirm"
                         IsModal="True"
                         IsLightDismissEnabled="True"
                         Style="Confirm"
                         MinWidth="400">
            <atom:MessageBox.CustomButtons>
                <atom:DialogButton Role="ActionRole">Custom Button</atom:DialogButton>
            </atom:MessageBox.CustomButtons>
            <StackPanel Spacing="5">
                <TextBlock>Bla bla ...</TextBlock>
            </StackPanel>
        </atom:MessageBox>
    </Panel>
</StackPanel>
```

code-behind文件：
```csharp
using System.Reactive.Disposables;
using AtomUI.Controls;
using AtomUIGallery.ShowCases.ViewModels;
using Avalonia.Interactivity;
using Avalonia.ReactiveUI;
using Avalonia.Threading;
using ReactiveUI;

namespace AtomUIGallery.ShowCases.Views;

public partial class ModalShowCase : ReactiveUserControl<ModalViewModel>
{
    public ModalShowCase()
    {
        this.WhenActivated(disposables =>
        {
            BasicOpenModalButton.Click       += HandleBasicModalButtonClick;
            BasicWindowOpenModalButton.Click += HandleBasicWindowModalButtonClick;

            ConfirmMsgBoxBtn.Click                   += HandleConfirmMsgBoxBtnClick;
            InformationMsgBoxBtn.Click               += HandleInformationMsgBoxBtnClick;
            SuccessMsgBoxBtn.Click                   += HandleSuccessMsgBoxBtnClick;
            ErrorMsgBoxBtn.Click                     += HandleErrorMsgBoxBtnClick;
            WarningMsgBoxBtn.Click                   += HandleWarningMsgBoxBtnClick;
            StyleCaseHostTypeSwitch.IsCheckedChanged += HandleStyleCaseHostTypeSwitchChanged;
            LoadingDialogOpenModalButton.Click       += HandleLoadingDialogOpenModalButtonClick;
            AsyncDialogOpenModalButton.Click         += HandleAsyncDialogOpenModalButtonClick;
            CustomFooterDialogOpenButton.Click       += HandleCustomFooterDialogOpenButtonClick;
            CustomFooterMsgBoxOpenButton.Click       += HandleCustomFooterMsgBoxOpenButtonClick;
            DraggableDialogOpenButton.Click          += HandleDraggableMsgBoxOpenButtonClick;
            DelayedCloseMsgBoxOpenButton.Click       += HandleDelayedCloseMsgBoxOpenButtonClick;
            ConfigureButtonsDialogOpenButton.Click   += HandleConfigureButtonsDialogButtonClick;
            
            disposables.Add(Disposable.Create(() => BasicOpenModalButton.Click       -= HandleBasicModalButtonClick));
            disposables.Add(Disposable.Create(() => BasicWindowOpenModalButton.Click -= HandleBasicWindowModalButtonClick));
            disposables.Add(Disposable.Create(() => ConfirmMsgBoxBtn.Click -= HandleConfirmMsgBoxBtnClick));
            disposables.Add(Disposable.Create(() => InformationMsgBoxBtn.Click -= HandleInformationMsgBoxBtnClick));
            disposables.Add(Disposable.Create(() => SuccessMsgBoxBtn.Click -= HandleSuccessMsgBoxBtnClick));
            disposables.Add(Disposable.Create(() => ErrorMsgBoxBtn.Click -= HandleErrorMsgBoxBtnClick));
            disposables.Add(Disposable.Create(() => WarningMsgBoxBtn.Click -= HandleWarningMsgBoxBtnClick));
            disposables.Add(Disposable.Create(() => StyleCaseHostTypeSwitch.IsCheckedChanged -= HandleStyleCaseHostTypeSwitchChanged));
            disposables.Add(Disposable.Create(() => LoadingDialogOpenModalButton.Click -= HandleLoadingDialogOpenModalButtonClick));
            disposables.Add(Disposable.Create(() => CustomFooterDialogOpenButton.Click -= HandleCustomFooterDialogOpenButtonClick));
            disposables.Add(Disposable.Create(() => CustomFooterMsgBoxOpenButton.Click -= HandleCustomFooterMsgBoxOpenButtonClick));
            disposables.Add(Disposable.Create(() => DraggableDialogOpenButton.Click -= HandleDraggableMsgBoxOpenButtonClick));
            disposables.Add(Disposable.Create(() => DelayedCloseMsgBoxOpenButton.Click -= HandleDelayedCloseMsgBoxOpenButtonClick));
            disposables.Add(Disposable.Create(() => ConfigureButtonsDialogOpenButton.Click -= HandleConfigureButtonsDialogButtonClick));

            ConfigureButtonPropertiesDialog.ButtonsConfigure = ConfigureButtonProperties;
            
            if (DataContext is ModalViewModel viewModel)
            {
                viewModel.MessageBoxStyleCaseHostType = DialogHostType.Overlay;
                viewModel.CountdownSeconds            = 5;
            }
        });
        InitializeComponent();
    }

    private void HandleBasicModalButtonClick(object? sender, RoutedEventArgs e)
    {
        if (DataContext is ModalViewModel viewModel)
        {
            viewModel.IsBasicModalOpened = true;
        }
    }
    
    private void HandleBasicWindowModalButtonClick(object? sender, RoutedEventArgs e)
    {
        if (DataContext is ModalViewModel viewModel)
        {
            viewModel.IsBasicWindowModalOpened = true;
        }
    }
    
    private void HandleConfirmMsgBoxBtnClick(object? sender, RoutedEventArgs e)
    {
        if (DataContext is ModalViewModel viewModel)
        {
            viewModel.IsConfirmMsgBoxOpened = true;
        }
    }
    
    private void HandleInformationMsgBoxBtnClick(object? sender, RoutedEventArgs e)
    {
        if (DataContext is ModalViewModel viewModel)
        {
            viewModel.IsInformationMsgBoxOpened = true;
        }
    }
    
    private void HandleSuccessMsgBoxBtnClick(object? sender, RoutedEventArgs e)
    {
        if (DataContext is ModalViewModel viewModel)
        {
            viewModel.IsSuccessMsgBoxOpened = true;
        }
    }
    
    private void HandleErrorMsgBoxBtnClick(object? sender, RoutedEventArgs e)
    {
        if (DataContext is ModalViewModel viewModel)
        {
            viewModel.IsErrorMsgBoxOpened = true;
        }
    }
    
    private void HandleWarningMsgBoxBtnClick(object? sender, RoutedEventArgs e)
    {
        if (DataContext is ModalViewModel viewModel)
        {
            viewModel.IsWarningMsgBoxOpened = true;
        }
    }

    private void HandleStyleCaseHostTypeSwitchChanged(object? sender, RoutedEventArgs e)
    {
        if (sender is ToggleSwitch toggleSwitch)
        {
            if (DataContext is ModalViewModel viewModel)
            {
                viewModel.MessageBoxStyleCaseHostType = toggleSwitch.IsChecked == true ? DialogHostType.Window : DialogHostType.Overlay;
            }
        }
    }
    
    private void HandleLoadingDialogOpenModalButtonClick(object? sender, RoutedEventArgs e)
    {
        if (DataContext is ModalViewModel viewModel)
        {
            viewModel.IsLoadingMsgBoxOpened = true;
        }
    }

    private void HandleLoadingDialogOpened(object? sender, EventArgs e)
    {
        if (sender is Dialog dialog)
        {
            DispatcherTimer.RunOnce(() =>
            {
                dialog.IsLoading = false;
            }, TimeSpan.FromMilliseconds(3000));
        }
    }

    private void HandleLoadingDialogButtonClicked(object? sender, DialogButtonClickedEventArgs e)
    {
        if (sender is Dialog dialog)
        {
            dialog.IsLoading = true;
            DispatcherTimer.RunOnce(() =>
            {
                dialog.IsLoading = false;
            }, TimeSpan.FromMilliseconds(3000));
        }
    }
    
    private void HandleAsyncDialogOpenModalButtonClick(object? sender, RoutedEventArgs e)
    {
        if (DataContext is ModalViewModel viewModel)
        {
            viewModel.IsAsyncDialogOpened = true;
        }
    }
    
    private void HandleAsyncDialogButtonClicked(object? sender, DialogButtonClickedEventArgs e)
    {
        if (sender is Dialog dialog && e.SourceButton.Role == DialogButtonRole.AcceptRole)
        {
            dialog.IsConfirmLoading = true;
            e.Handled               = true;
            DispatcherTimer.RunOnce(() =>
            {
                dialog.IsConfirmLoading = false;
                dialog.Done();
            }, TimeSpan.FromMilliseconds(3000));
        }
    }

    private void HandleCustomFooterDialogOpenButtonClick(object? sender, EventArgs e)
    {
        if (DataContext is ModalViewModel viewModel)
        {
            viewModel.IsCustomFooterDialogOpened = true;
        }
    }

    private void HandleCustomFooterMsgBoxOpenButtonClick(object? sender, EventArgs e)
    {
        if (DataContext is ModalViewModel viewModel)
        {
            viewModel.IsCustomFooterMsgBoxOpened = true;
        }
    }
    
    private void HandleDraggableMsgBoxOpenButtonClick(object? sender, EventArgs e)
    {
        if (DataContext is ModalViewModel viewModel)
        {
            viewModel.IsDraggableMsgBoxOpened = true;
        }
    }
    
    private void HandleDelayedCloseMsgBoxOpenButtonClick(object? sender, EventArgs e)
    {
        if (DataContext is ModalViewModel viewModel)
        {
            viewModel.IsDelayedCloseMsgBoxOpened = true;
        }
    }

    private IDisposable? _delayedCloseDialogDisposal;
    
    private void HandleDelayedCloseMsgBoxOpened(object? sender, EventArgs e)
    {
        if (sender is MessageBox messageBox)
        {
            if (DataContext is ModalViewModel viewModel)
            {
                viewModel.CountdownSeconds = 5;
                _delayedCloseDialogDisposal?.Dispose();
                _delayedCloseDialogDisposal = DispatcherTimer.Run(() =>
                {
                    if (viewModel.CountdownSeconds == 0)
                    {
                        messageBox.Confirm();
                        return false;
                    }
                    viewModel.CountdownSeconds--;
                    return true;
                }, TimeSpan.FromMilliseconds(1000));
            }
        }
    }
    
    private void HandleConfigureButtonsDialogButtonClick(object? sender, EventArgs e)
    {
        if (DataContext is ModalViewModel viewModel)
        {
            viewModel.IsConfigureButtonsDialogOpened = true;
        }
    }

    private void ConfigureButtonProperties(IReadOnlyList<DialogButton> buttons)
    {
        foreach (var button in buttons)
        {
            button.IsEnabled = false;
        }
    }
}
```

view-model文件：
```csharp
using AtomUI.Controls;
using ReactiveUI;

namespace AtomUIGallery.ShowCases.ViewModels;

public class ModalViewModel : ReactiveObject, IRoutableViewModel
{
    public const string ID = "Modal";
    
    public IScreen HostScreen { get; }
    
    public string UrlPathSegment { get; } = ID;
    
    private bool _isBasicModalOpened;

    public bool IsBasicModalOpened
    {
        get => _isBasicModalOpened;
        set => this.RaiseAndSetIfChanged(ref _isBasicModalOpened, value);
    }

    private bool _isBasicWindowModalOpened;

    public bool IsBasicWindowModalOpened
    {
        get => _isBasicWindowModalOpened;
        set => this.RaiseAndSetIfChanged(ref _isBasicWindowModalOpened, value);
    }
    
    private DialogHostType _messageBoxStyleCaseHostType;

    public DialogHostType MessageBoxStyleCaseHostType
    {
        get => _messageBoxStyleCaseHostType;
        set => this.RaiseAndSetIfChanged(ref _messageBoxStyleCaseHostType, value);
    }
   
    private bool _isConfirmMsgBoxOpened;

    public bool IsConfirmMsgBoxOpened
    {
        get => _isConfirmMsgBoxOpened;
        set => this.RaiseAndSetIfChanged(ref _isConfirmMsgBoxOpened, value);
    }
    
    private bool _isInformationMsgBoxOpened;

    public bool IsInformationMsgBoxOpened
    {
        get => _isInformationMsgBoxOpened;
        set => this.RaiseAndSetIfChanged(ref _isInformationMsgBoxOpened, value);
    }
    
    private bool _isSuccessMsgBoxOpened;

    public bool IsSuccessMsgBoxOpened
    {
        get => _isSuccessMsgBoxOpened;
        set => this.RaiseAndSetIfChanged(ref _isSuccessMsgBoxOpened, value);
    }
        
    private bool _isErrorMsgBoxOpened;

    public bool IsErrorMsgBoxOpened
    {
        get => _isErrorMsgBoxOpened;
        set => this.RaiseAndSetIfChanged(ref _isErrorMsgBoxOpened, value);
    }
    
    private bool _isWarningMsgBoxOpened;

    public bool IsWarningMsgBoxOpened
    {
        get => _isWarningMsgBoxOpened;
        set => this.RaiseAndSetIfChanged(ref _isWarningMsgBoxOpened, value);
    }
    
    private bool _isLoadingMsgBoxOpened;

    public bool IsLoadingMsgBoxOpened
    {
        get => _isLoadingMsgBoxOpened;
        set => this.RaiseAndSetIfChanged(ref _isLoadingMsgBoxOpened, value);
    }
    
    private bool _isAsyncDialogOpened;

    public bool IsAsyncDialogOpened
    {
        get => _isAsyncDialogOpened;
        set => this.RaiseAndSetIfChanged(ref _isAsyncDialogOpened, value);
    }
    
    private bool _isCustomFooterDialogOpened;

    public bool IsCustomFooterDialogOpened
    {
        get => _isCustomFooterDialogOpened;
        set => this.RaiseAndSetIfChanged(ref _isCustomFooterDialogOpened, value);
    }
    
    private bool _isCustomFooterMsgBoxOpened;

    public bool IsCustomFooterMsgBoxOpened
    {
        get => _isCustomFooterMsgBoxOpened;
        set => this.RaiseAndSetIfChanged(ref _isCustomFooterMsgBoxOpened, value);
    }
    
    private bool _isDraggableMsgBoxOpened;

    public bool IsDraggableMsgBoxOpened
    {
        get => _isDraggableMsgBoxOpened;
        set => this.RaiseAndSetIfChanged(ref _isDraggableMsgBoxOpened, value);
    }
    
    private bool _isDelayedCloseMsgBoxOpened;

    public bool IsDelayedCloseMsgBoxOpened
    {
        get => _isDelayedCloseMsgBoxOpened;
        set => this.RaiseAndSetIfChanged(ref _isDelayedCloseMsgBoxOpened, value);
    }
    
    private int _countdownSeconds;

    public int CountdownSeconds
    {
        get => _countdownSeconds;
        set => this.RaiseAndSetIfChanged(ref _countdownSeconds, value);
    }
    
    private bool _isConfigureButtonsDialogOpened;

    public bool IsConfigureButtonsDialogOpened
    {
        get => _isConfigureButtonsDialogOpened;
        set => this.RaiseAndSetIfChanged(ref _isConfigureButtonsDialogOpened, value);
    }
    
    public ModalViewModel(IScreen screen)
    {
        HostScreen = screen;
    }
}
```
