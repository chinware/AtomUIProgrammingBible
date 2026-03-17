# Pagination 概述

### 简介

Pagination 分页组件用于在数据量较大时对内容进行分页展示，帮助用户在多页数据间快速导航。当数据条目较多、需要分段加载或展示时，分页组件可以有效提升用户的浏览体验。

![AtomUI Pagination组件](./images/basic.webp)

### 主要功能

* 基础分页，通过 `Total` 和 `CurrentPage` 控制页码
* 三种对齐方式（Start / Center / End）适配不同布局需求
* 页面大小选择器（IsShowSizeChanger），允许用户动态调整每页条目数
* 快速跳转（IsShowQuickJumper），支持用户直接输入页码跳转
* 总数信息展示（IsShowTotalInfo），并支持通过 `TotalInfoTemplate` 自定义模板
* 简洁模式（SimplePagination），适用于空间有限的场景
* 支持小尺寸（SizeType="Small"）与禁用状态
