---
title: "如何定义业务活动 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- business activities, creating [Excel add-in]
- monitoring business activities [BAM], creating business activities [Excel add-in]
- monitoring business activities [BAM], Excel add-in
ms.assetid: 305e3718-46b4-45df-bd52-f7ae36621576
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 74cb0bb6f2bd0a5f92f6029dda65d55d219bcc12
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-define-a-business-activity"></a>如何定义业务活动
要表示需要为报告收集的数据，必须定义 BAM 活动。 这包含了您希望 BAM 跟踪的一系列重要的里程碑和数据项。可以使用 BAM Excel 外接程序创建活动，详见以下步骤中的说明。  
  
> [!NOTE]
>  部署某个活动后，对该活动可执行的操作就会受到限制。 具体而言，除非准备让管理员取消部署整个 BAM 活动和视图集，然后重新部署它们，否则，您无法从活动中删除项。 这可能导致查看中断和数据丢失，除非管理员进行数据备份和还原。  
  
### <a name="to-create-a-business-activity"></a>创建业务活动  
  
1.  打开 Microsoft Excel。  
  
2.  在工具菜单栏上，单击**BAM**菜单项，并单击**BAM 活动**。  
  
     **业务活动监视活动向导**显示。  
  
3.  单击**新活动**。  
  
     **新活动**对话框随即出现。  
  
4.  键入中的活动的描述性名称**活动名称**文本框。  
  
> [!NOTE]
>  活动必须至少包含一个活动项。  
  
#### <a name="to-create-a-new-item"></a>创建新项  
  
1.  单击**新项**。  
  
2.  在**新活动项**对话框中，在**新活动项**框中，键入活动项目的描述性名称。  
  
3.  从**项目类型**下拉菜单中，选择此项类型。 可能的值包括：  
  
    |项类型|Description|  
    |---------------|-----------------|  
    |业务里程碑|日期/时间值。 例如，采购订单的批准日期。|  
    |业务数据 – Text|包含任何字母数字的字符串。 例如，交付到： 城市、 省/市/自治区和邮政编码代码。|  
    |业务数据 – 整数|一个整数值。 例如，购买的总量。|  
    |业务数据 – Decimal|一个十进制值。 例如，PO 的美元总金额。|  
  
     如果你选择的项目类型"业务数据 – Text"时，你必须输入中的字符串的最大字符数**最大长度**框。  
  
    > [!NOTE]
    >  有关创建这些项的详细信息，请参阅 Microsoft BizTalk Server 教程中的“合作伙伴管理和业务活动监视”。  
  
4.  重复步骤 1 至 3，可向此活动中添加所需数量的项。  
  
5.  完成“业务活动监视活动向导”后，“业务活动监视视图向导”将自动启动。  
  
 有关使用此向导的详细信息，请参阅[定义 BAM 视图](../core/defining-a-bam-view.md)。  
  
## <a name="see-also"></a>另请参阅  
 [定义 BAM 视图](../core/defining-a-bam-view.md)   
 [在 Excel 中定义的业务活动和视图](../core/defining-business-activities-and-views-in-excel.md)