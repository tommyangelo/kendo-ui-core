---
title: Cascade the DropDownList with Enabled Virtualization
page_title: Cascade DropDownList widget with enabled virtualization
description: Cascade DropDownList widget with enabled virtualization
---

# Cascade the DropDownList with Enabled Virtualization

This project demonstrates how to use to cascade dropdownlist widgets and still virtualize the data. The implementation is pretty simple, because in the case of virtualization a custom data source configuration is used,
which enables the usage of `DataSourceRequest` and `ToDataSourceResult` methods, which internally will parse all filter and page expression information and will apply it directly to the data.

[Cascade the DropDownList with enabled virtualization](https://github.com/telerik/ui-for-aspnet-mvc-examples/tree/master/dropdownlist/KendoDropDownListCascadingAndVirtualization)
