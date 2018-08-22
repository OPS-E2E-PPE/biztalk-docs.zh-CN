---
title: 脚本 Functoid |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Scripting functoids, about Scripting functoids
- Scripting functoids
- Scripting functoids, configuring
ms.assetid: ea8353da-049b-4e0c-a700-f51708db22a3
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b26223884bce626404586115da36ff7989ac13b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982350"
---
# <a name="scripting-functoid"></a>“脚本”Functoid
**脚本**functoid，您可以使用自定义脚本或代码在运行时执行功能不可用。 例如，可以通过调用.NET 程序集在运行时**脚本**functoid 并编写您自己的自定义函数。  
  
 **脚本**functoid 支持以下语言：  
  
- C# .NET  
  
- JScript .NET  
  
- Visual Basic .NET  
  
- 可扩展样式表语言转换 (XSLT)  
  
- XSLT 调用模板  
  
  当前的另一个显著区别**脚本**functoid 及更早版本是该脚本需要不再是创建并存储在该 functoid 本身中。 相反，您可以在单独的.NET 程序集中创建脚本并引用通过程序集**脚本**属性。 在单独的程序集中保存脚本使您能够在多个映射中使用同一脚本。 此外，您可能能够购买**脚本**functoid 程序集从第三方供应商。  
  
  可以使用**脚本**以前版本的 BizTalk 映射器与 BizTalk 映射器的当前版本中创建的 functoid。 但是，必须首先迁移这些 functoid。 有关如何迁移的详细信息**Scripting** functoid，请参阅[迁移 Functoid](../core/migrating-functoids.md)。  
  
  当您将添加**脚本**映射到 functoid，您需要配置该 functoid 使用的脚本。 如果选择**Scripting** functoid**脚本**属性中启用了**属性**窗口。 如果单击省略号 (**...**) 按钮为此属性，请**配置脚本 Functoid**对话框随即打开。 或者，也可以双击**脚本**functoid。  
  
  下表显示了此对话框的字段：  
  
|配置脚本 Functoid 对话框框字段|Description|  
|---------------------------------------------------|-----------------|  
|**选择脚本类型**|使用此字段来选择你想要使用在此脚本的类型**脚本**functoid。<br /><br /> 值：<br /><br /> -   **外部程序集**。 使用此值，如果你想要将相关联**脚本**functoid 与全局程序集缓存 (GAC) 中的程序集。 **警告：** 中外部程序集的代码必须是线程安全。 在任务繁忙时，可以同时运行多个映射实例。<br />-   **内联 C#**。  使用此值，如果你想要将相关联**Scripting**中的 C# 代码的 functoid**内联脚本**缓冲区。<br />-   **内联 JScript.NET**。 使用此值，如果你想要将相关联**Scripting** functoid 与中的 JScript.NET 脚本**内联脚本**缓冲区。<br />-   **内联 Visual Basic.NET**。 使用此值，如果你想要将相关联**Scripting** functoid 中的 Visual Basic.NET 代码与**内联脚本**缓冲区。<br />-   **内联 XSLT**。 使用此值，如果你想要将相关联**Scripting** functoid 与中的 XSLT**内联脚本**缓冲区。<br />-   **内联 XSLT 调用模板**。 使用此值，如果你想要将相关联**Scripting** functoid 与中的 XSLT 调用模板**内联脚本**缓冲区。|  
|**脚本程序集**|选择要将与相关联的程序集**脚本**functoid。 只有在“项目”窗口中引用的程序集才会显示在此列表中。 另外请注意，必须在 GAC 中注册程序集。<br /><br /> 此字段才可用**选择脚本类型**设置为**外部程序集**。|  
|**脚本类**|选择希望此程序集中所选的类**脚本**functoid 使用。<br /><br /> 此字段才可用**选择脚本类型**设置为**外部程序集**。|  
|**脚本方法**|选择希望此所选类中的方法**脚本**functoid 使用。 **注意：** 请确保方法所需的输入参数的数目与输入参数中指定的数目匹配**配置脚本 Functoid**对话框。|  
|**内联脚本**|将要使用的内联脚本写入或复制到此文本框中。 有效的语言和脚本包括：C#、JScript .NET、Visual Basic .NET、XSLT 和 XSLT 调用模板。<br /><br /> 此字段才可用**选择脚本类型**设置为之一**内联**设置。 **注意：** 避免多次使用相同的方法签名。 如果多个“脚本”functoid 具有相同的方法签名，则 BizTalk 会选择实现的第一个方法签名，而忽略其他签名。|  
  
 下图显示了如何**脚本**functoid 显示在使用 C#.Net 脚本重新设置电话号码的格式的映射。  
  
 ![使用 C 将映射&#35;若要设置格式的电话号码。](../core/media/scriptingfunctoid.gif "scriptingfunctoid")  
“脚本”Functoid 映射  
  
## <a name="in-this-section"></a>本节内容  
  
-   [使用外部程序集编写脚本](../core/scripting-using-external-assemblies.md)  
  
-   [使用内联 C#、JScript .NET 和 Visual Basic .NET 编写脚本](../core/scripting-using-inline-csharp-jscript-net-and-visual-basic-net.md)  
  
-   [使用内联 XSLT 和 XSLT 调用模板编写脚本](../core/scripting-using-inline-xslt-and-xslt-call-templates.md)