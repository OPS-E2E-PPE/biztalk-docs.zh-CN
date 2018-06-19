---
title: 如何在向地图添加脚本 Functoid |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.mapper.functiod.script
ms.assetid: eb96814a-b3fb-48f6-a947-ab595a270faa
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e66e6ed25fd44b1e89fe5500346a7ad01d5d7ff0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248469"
---
# <a name="how-to-add-scripting-functoids-to-a-map"></a>如何向映射添加“脚本”Functoid
**脚本**functoid，可使用自定义脚本或代码在运行时执行功能不可用。 例如，通过使用，在运行时调用的 COM 对象**脚本**functoid 和编写您自己的自定义脚本。  
  
 有关概念性信息**脚本**functoid，请参阅[脚本 Functoid](../core/scripting-functoid.md)。  
  
### <a name="to-add-the-scripting-functoid-to-a-map-and-configure-it"></a>向映射添加“脚本”functoid 并对其进行配置  
  
1.  与[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]工具箱处于活动状态，单击**高级 Functoid**选项卡以选择 functoid 该类别。  
  
     此时，将显示所选类别的高级 functoid 列表。  
  
2.  拖动**脚本**functoid![](../core/media/bts-tls-scripting.gif "bts_tls_scripting")从工具箱拖到网格页上的适当位置。  
  
    > [!NOTE]
    >  该 functoid 将放置到显示的网格页上。 如果你想要将 functoid 放到不同的网格页面上，你需要首先显示其他网格该页。  
  
    > [!NOTE]
    >  如果你在构造结合使用多个 functoid 的映射，你需要考虑它们相对的从左到右位置。 Functoid 是按照从左到右的顺序执行的。 一个 functoid 的输出只能输入到其右侧的另一个 functoid 中。  
  
3.  选择**脚本**functoid 刚才添加到显示的网格页。  
  
4.  在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]属性窗口中，单击省略号 (**...**) 与关联的按钮**脚本**属性。  
  
    > [!NOTE]
    >  或者，你可以右键单击提取 functoid，，然后单击**配置 Functoid 脚本**上下文菜单中。 **配置脚本 Functoid**对话框中将显示**脚本 Functoid 配置**选定选项卡。  
  
5.  在**配置脚本 Functoid**对话框中，在**选择脚本类型**下拉列表中，选择你的脚本的类型。  
  
    > [!NOTE]
    >  根据所选择的脚本类型，将启用和禁用剩余对话框字段的不同子集。  
  
6.  如果你选择**外部程序集**作为脚本类型，使用**脚本程序集**，**脚本类**，和**脚本方法**下拉列表表，请在该顺序，以选择程序集、 类和方法，分别与此关联**脚本**functoid。  
  
    > [!WARNING]
    >  外部程序集中的代码必须为线程安全代码。 在任务繁忙时，可以同时运行多个映射实例。  
  
    > [!NOTE]
    >  选择一个程序集后,**脚本类**下拉列表中会填入中该程序集的类。 同样，之后你已选择一个类，**脚本方法**下拉列表将使用该类中的方法进行填充。  
  
    > [!NOTE]
    >  **内联脚本**文本框被禁用，当你选择**外部程序集**作为脚本类型。  
  
     如果选择了命令以外**外部程序集**作为脚本类型 （其中一个内联选项），使用**内联脚本**文本框中，在你所选的语言中输入你的脚本。  
  
    > [!NOTE]
    >  为内联语言选择**脚本**functoid 包括 C#.NET、 JScript.NET、 Visual Basic.NET、 XSLT 和 XSLT 调用模板。  
  
     使用 C# 编写脚本时不允许使用“using”语句。 如果脚本需要使用任何特殊的 .Net 类，则应将相应的程序集及其依存程序集添加到 BizTalk 项目的“参考”中，并且脚本代码应该使用完全限定的名称。 如果您编写一个执行区分区域性的小写转换脚本，应按如下所示编写相应的代码段。 类似限制适用于所有受支持的脚本语言。  
  
    ```  
    string x = y.ToLower(System.Globalization.CultureInfo.CurrentCulture);  
    ```  
  
     在脚本中，若要使用任何程序集中的类，请确保将相应程序集及其依存程序集添加到包含映射的 BizTalk 项目的“参考”中。  
  
    > [!NOTE]
    >  你可以创建自定义脚本中直接在**内联脚本**文本框中，或者你可以创建你的脚本在其他位置，并将其粘贴到**内联脚本**文本框。  
  
    > [!NOTE]
    >  **脚本程序集**，**脚本类**，和**脚本方法**当你选择的内联选项之一时，会禁用的下拉列表 (内容以外**外部程序集**) 作为脚本类型。  
  
    > [!IMPORTANT]
    >  如果创建包含多个函数的脚本，则第一个函数将被视为主函数，其余函数只在执行主函数时进行调用。  
  
     单击 **“确定”**。  
  
7.  如果外部程序集中的脚本或相关方法需要输入参数，请创建相应数量和类型的输入链接（就像使用基本 functoid 一样）。  
  
8.  在大多数情况下，你**脚本**functoid 将产生输出值用于填充目标架构中的字段或作为另一个 functoid 的输入，在很多相同方式该基本 functoid 执行。  
  
## <a name="see-also"></a>另请参阅  
 [向地图添加高级的 Functoid](../core/adding-advanced-functoids-to-a-map.md)