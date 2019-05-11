---
title: 如何向映射添加基本 Functoid |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6a81fb73-cccf-4f74-af92-39e4af13e255
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94787a629fcdea0c061a73e04de127acb1deea96
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65343401"
---
# <a name="how-to-add-basic-functoids-to-a-map"></a>如何向映射添加基本 Functoid
许多 functoid 都十分易于使用。 这些内容称为到此处以将它们与中的 functoid 区分开来的基本 functoid**高级**类别。 基本 functoid 组成的其余类别的 functoid 如转换、 累计、 数据库、 日期和时间、 判断、 数学、 科学记数，以及字符串。  
  
 基本 functoid，一般情况下，具有简单类型，如数字和字符串，作为其输入和输出链接。  
  
 基本 functoid 的使用涉及到将其添加到网格页上，创建来自左侧，并从离开至右侧的 functoid 创建输出链接的 functoid 的输入的链接。 本主题提供有关这些操作的分步说明。  
  
## <a name="add-a-basic-functoid-to-a-map"></a>向映射添加基本 functoid  
  
1. 使用[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]工具箱处于活动状态，请单击相应的选项卡，选择你想要使用的 functoid 的类别。  
  
    显示所选类别中的可用 functoid 的列表。  
  
2. 你想要从工具箱拖到网格页上的相应位置使用的 functoid 拖。  
  
   > [!NOTE]
   >  该 functoid 将放置上显示的网格页。 如果你想要将该 functoid 放置到其他网格页上，您需要首先显示该其他网格页。  
  
   > [!NOTE]
   >  如果构造一起使用多个 functoid 的映射，您需要考虑它们的左右位置关系。 从左向右执行 Functoid。 Functoid 的输出只能输入到其右侧的另一个 functoid。  
  
## <a name="create-input-links-to-a-basic-functoid"></a>创建指向基本 functoid 的输入的链接  
  
1. 将记录或字段节点从源架构拖到显示的网格页中的基本 functoid。  
  
    **- Or -**  
  
    在显示的网格页中，将位于左侧，另一个 functoid 拖到你想要创建输入的链接的基本 functoid。  
  
    **- Or -**  
  
    将在显示的网格页中的基本 functoid 拖至源架构中的记录或字段节点。  
  
    **- Or -**  
  
    在显示的网格页中，将你想要创建输入的链接指向所在的另一个 functoid 左侧的基本 functoid。  
  
   > [!NOTE]
   >  拖动时，该链接，而不是链接的锚定终结点的移动终结点更改为十字线图标，以便可以更准确地对准第二个终结点。 如果鼠标悬停在一个对象，该链接相应的第二个终结点，如可能发生数据类型不匹配时的链接的移动终结点，十字线图标更改为显示带有贯穿斜线的圆形图标。  
  
2. 根据需要来建立指向基本 functoid 的输入链接的完整集合 （尽管可能不是全部输入参数的集合） 重复步骤 1。  
  
   > [!NOTE]
   >  有几个不需要任何输入的链接的 functoid。 例如，**日期**，**时间**，并**日期和时间**中的 functoid**日期和时间**functoid 类别提供当前日期时间或日期和时间，分别在其处理实例消息。 因此，它们不需要将源架构中的任何输入的参数。  
   > 
   > [!NOTE]
   >  许多 functoid 的输入参数的顺序非常重要，如相应的 functoid 参考主题中所述 (请参阅**Functoid 参考** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)])。 创建链接的顺序设置为提取 functoid 的输入参数的顺序。 有关 functoid 属性和指定 functoid 输入参数的顺序的详细信息，请参阅[编辑 Functoid 属性和输入参数](../core/editing-functoid-properties-and-input-parameters.md)。 有关如何配置 functoid 的输入的参数的信息，请参阅[如何配置 Functoid 输入参数](../core/how-to-configure-functoid-input-parameters.md)。  
   > 
   > [!NOTE]
   >  确保你想要链接的 functoid 或源架构节点可见在显示的网格页或源架构窗口中开始进行链接之前。  
  
## <a name="create-the-output-link-from-a-basic-functoid"></a>从基本 functoid 创建输出链接  
  
1.  将将目标架构中的记录或字段节点拖到显示的网格页中的基本 functoid 中。  
  
     **- Or -**  
  
     在显示的网格页中，将位于的权限，你想要创建输出链接的基本 functoid 的另一个 functoid。  
  
     **- Or -**  
  
     将在显示的网格页中的基本 functoid 拖至目标架构中的记录或字段节点。  
  
     **- Or -**  
  
2.  在显示的网格页中，将你想要创建的输出链接指向另一个 functoid，它位于其右侧的基本 functoid。  
  
    > [!NOTE]
    >  确保你想要链接的 functoid 和源架构节点已经可见在显示的网格页中和源架构窗口中，分别在开始链接操作之前。  
  
    > [!NOTE]
    >  Functoid 链接始终尝试禁止不适当的链接，如链接源和目标数据类型不匹配。  
  
    > [!NOTE]
    >  拖动时，该链接，而不是链接的锚定终结点的移动终结点更改为十字线图标，以便可以更准确地对准第二个终结点。 如果鼠标悬停在一个对象，该链接相应的第二个终结点，如可能发生数据类型不匹配时的链接的移动终结点，十字线图标更改为显示带有贯穿斜线的圆形图标。  
  
## <a name="see-also"></a>请参阅  
**Functoid 参考** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]