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
ms.openlocfilehash: c033ce9dff8b5d9a07dca574d089f575b4eaa5e9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008934"
---
# <a name="how-to-add-basic-functoids-to-a-map"></a>如何向映射添加基本 Functoid
许多 functoid 都十分易于使用。 这些内容称为到此处以将它们与中的 functoid 区分开来的基本 functoid**高级**类别。 基本 functoid 由除“高级”之外的其余类别的 functoid 组成，例如“转换”、“累计”、“数据库”、“日期和时间”、“判断”、“数学”、“科学计数法”和“字符串”。  
  
 通常，基本 functoid 会使用简单类型（例如数字和字符串）作为其输入链接和输出链接。  
  
 基本 functoid 的使用包含将其添加到网格页、创建来自左侧并指向该 functoid 的输入链接、创建来自该 functoid 并离开至右侧的输出链接。 本主题提供有关这些操作的分步说明。  
  
## <a name="add-a-basic-functoid-to-a-map"></a>向映射添加基本 functoid  
  
1. 使用[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]工具箱处于活动状态，请单击相应的选项卡，选择你想要使用的 functoid 的类别。  
  
    此时，将显示所选类别的可用 functoid 的列表。  
  
2. 将要使用的 functoid 从工具箱中拖至网格页上的适当位置。  
  
   > [!NOTE]
   >  该 functoid 将放置到显示的网格页上。 如果你想要将该 functoid 放置到其他网格页上，您需要首先显示该其他网格页。  
  
   > [!NOTE]
   >  如果是构造使用多个 functoid 的映射，则需要考虑它们的左右位置关系。 Functoid 是按照从左到右的顺序执行的。 一个 functoid 的输出只能输入到其右侧的另一个 functoid 中。  
  
## <a name="create-input-links-to-a-basic-functoid"></a>创建指向基本 functoid 的输入的链接  
  
1. 将源架构中的记录或字段节点拖至所显示的网格页中的基本 functoid。  
  
    **-或者-**  
  
    在所显示的网格页中，将位于左侧的另一个 functoid 拖至要创建的输入链接指向的基本 functoid。  
  
    **-或者-**  
  
    将所显示的网格页中的基本 functoid 拖至源架构中的记录或字段节点。  
  
    **-或者-**  
  
    在所显示的网格页中，将要创建的输入链接指向的基本 functoid 拖至位于其左侧的另一个 functoid。  
  
   > [!NOTE]
   >  拖动时，该链接，而不是链接的锚定终结点的移动终结点更改为十字线图标，以便可以更准确地对准第二个终结点。 如果将链接的移动终结点悬停在某个对象上，而该对象不适合作为该链接的第二个终结点（例如，如果存在数据类型不匹配，则可能出现此情况），则十字线图标将更改为显示带有贯穿斜线的圆形的图标。  
  
2. 根据需要重复步骤 1 以建立指向基本 functoid 的输入链接的完整集（尽管可能不是全部输入参数的集合）。  
  
   > [!NOTE]
   >  少数 functoid 不需要任何输入链接。 例如，**日期**，**时间**，并**日期和时间**中的 functoid**日期和时间**functoid 类别提供当前日期时间或日期和时间，分别在其处理实例消息。 因此，这些 functoid 不需要来自源架构的任何输入参数。  
   > 
   > [!NOTE]
   >  许多 functoid 的输入参数的顺序非常重要，如相应的 functoid 参考主题中所述 (请参阅**Functoid 参考** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)])。 创建链接的顺序规定了该 functoid 的输入参数的顺序。 有关 functoid 属性和指定 functoid 输入参数的顺序的详细信息，请参阅[编辑 Functoid 属性和输入参数](../core/editing-functoid-properties-and-input-parameters.md)。 有关如何配置 functoid 的输入的参数的信息，请参阅[如何配置 Functoid 输入参数](../core/how-to-configure-functoid-input-parameters.md)。  
   > 
   > [!NOTE]
   >  确保在开始进行链接之前，要链接的 functoid 或源架构的节点在所显示的网格页或源架构窗口中可见。  
  
## <a name="create-the-output-link-from-a-basic-functoid"></a>从基本 functoid 创建输出链接  
  
1.  将目标架构中的记录或字段节点拖至所显示的网格页中的基本 functoid。  
  
     **-或者-**  
  
     在所显示的网格页中，将位于右侧的另一个 functoid 拖至要创建的输出链接指向的基本 functoid。  
  
     **-或者-**  
  
     将所显示的网格页中的基本 functoid 拖至目标架构中的记录或字段节点。  
  
     **-或者-**  
  
2.  在所显示的网格页中，将要创建的输出链接指向的基本 functoid 拖至位于其右侧的另一个 functoid。  
  
    > [!NOTE]
    >  确保在开始进行链接操作之前，要链接的 functoid 和源架构的节点已分别在所显示的网格页中和源架构窗口中可见。  
  
    > [!NOTE]
    >  Functoid 链接会始终尝试禁止使用不适当的链接，例如其中的源数据类型与目标数据类型不匹配的链接。  
  
    > [!NOTE]
    >  在拖动过程中，链接的移动终结点（与该链接的锚定终结点相对应）将更改为十字线图标，以便可以更准确地对准第二个终结点。 如果将链接的移动终结点悬停在某个对象上，而该对象不适合作为该链接的第二个终结点（例如，如果存在数据类型不匹配，则可能出现此情况），则十字线图标将更改为显示带有贯穿斜线的圆形的图标。  
  
## <a name="see-also"></a>请参阅  
**Functoid 参考** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]