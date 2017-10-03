---
title: "脚本 Functoid |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Scripting functoids, about Scripting functoids
- Scripting functoids
- Scripting functoids, configuring
ms.assetid: ea8353da-049b-4e0c-a700-f51708db22a3
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 822bdbc4482a7e16a7458c7c44d128967203f283
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="scripting-functoid"></a>“脚本”Functoid
**脚本**functoid，可使用自定义脚本或代码在运行时执行功能不可用。 例如，你可以在运行时的.NET 程序集使用调用**脚本**functoid 和编写您自己的自定义函数。  
  
 **脚本**functoid 支持以下语言：  
  
-   C# .NET  
  
-   JScript .NET  
  
-   Visual Basic .NET  
  
-   可扩展样式表语言转换 (XSLT)  
  
-   XSLT 调用模板  
  
 当前的另一个显著区别**脚本**functoid 及更早版本是脚本需要不再是创建并存储在 functoid 本身。 相反，你可以在单独的.NET 程序集创建脚本，并引用程序集通过**脚本**属性。 在单独的程序集中保存脚本使您能够在多个映射中使用同一脚本。 此外，你可能能够购买**脚本**functoid 第三方供应商提供的程序集。  
  
 你可以使用**脚本**创建在 BizTalk 映射程序的当前版本的以前版本的 BizTalk 映射程序 functoid。 但是，必须首先迁移这些 functoid。 有关详细信息，有关如何迁移**脚本**functoid，请参阅[迁移 Functoid](../core/migrating-functoids.md)。  
  
 当你将添加**脚本**functoid 到图中的，你需要配置 functoid 使用的脚本。 如果你选择**脚本**functoid，**脚本**在中启用属性**属性**窗口。 如果单击省略号 (**...**) 为此属性的按钮**配置脚本 Functoid**对话框随即打开。 或者，你可以双击**脚本**functoid。  
  
 下表显示了此对话框的字段：  
  
|配置脚本 Functoid 对话框框字段|Description|  
|---------------------------------------------------|-----------------|  
|**选择脚本类型**|使用此字段来选择你想要使用此脚本的类型**脚本**functoid。<br /><br /> 值：<br /><br /> -   **外部程序集**。 使用此值，如果你想要关联**脚本**functoid 与在全局程序集缓存 (GAC) 中的程序集。 **警告：**外部程序集中的代码必须是线程安全。 在任务繁忙时，可以同时运行多个映射实例。<br />-   **内联 C#**。  使用此值，如果你想要关联**脚本**包含 C# 代码中的 functoid**内联脚本**缓冲区。<br />-   **内联 JScript.NET**。 使用此值，如果你想要关联**脚本**与中的 JScript.NET 脚本 functoid**内联脚本**缓冲区。<br />-   **内联 Visual 基本.NET**。 使用此值，如果你想要关联**脚本**与中的 Visual Basic.NET 代码的 functoid**内联脚本**缓冲区。<br />-   **内联 XSLT**。 使用此值，如果你想要关联**脚本**与中的 XSLT functoid**内联脚本**缓冲区。<br />-   **内联 XSLT 调用模板**。 使用此值，如果你想要关联**脚本**与中的 XSLT 调用模板的 functoid**内联脚本**缓冲区。|  
|**脚本程序集**|选择要将与相关联的程序集**脚本**functoid。 只有在“项目”窗口中引用的程序集才会显示在此列表中。 另外请注意，必须在 GAC 中注册程序集。<br /><br /> 此字段才可用**选择脚本类型**设置为**外部程序集**。|  
|**脚本类**|选择你想这选程序集内的类**脚本**functoid 来使用。<br /><br /> 此字段才可用**选择脚本类型**设置为**外部程序集**。|  
|**脚本方法**|选择你希望此所选的类中的方法**脚本**functoid 来使用。 **注意：**请确保被方法所期望的输入参数的数目匹配中指定的输入参数的数目**配置脚本 Functoid**对话框。|  
|**内联脚本**|将要使用的内联脚本写入或复制到此文本框中。 有效的语言和脚本包括：C#、JScript .NET、Visual Basic .NET、XSLT 和 XSLT 调用模板。<br /><br /> 此字段才可用**选择脚本类型**设置为之一**内联**设置。 **注意：**避免多次使用相同的方法签名。 如果多个“脚本”functoid 具有相同的方法签名，则 BizTalk 会选择实现的第一个方法签名，而忽略其他签名。|  
  
 下图显示了**脚本**functoid 出现在图中使用 C#.Net 脚本来重新设置格式的电话号码。  
  
 ![使用 c&#35; 的映射若要设置格式的电话号码。] (../core/media/scriptingfunctoid.gif "scriptingfunctoid")  
“脚本”Functoid 映射  
  
## <a name="in-this-section"></a>本节内容  
  
-   [脚本使用外部程序集](../core/scripting-using-external-assemblies.md)  
  
-   [脚本使用内联 C#、 JScript.NET 和 Visual Basic.NET](../core/scripting-using-inline-csharp-jscript-net-and-visual-basic-net.md)  
  
-   [脚本使用内联 XSLT 和 XSLT 调用模板](../core/scripting-using-inline-xslt-and-xslt-call-templates.md)