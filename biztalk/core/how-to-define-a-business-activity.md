---
title: 如何定义业务活动 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- business activities, creating [Excel add-in]
- monitoring business activities [BAM], creating business activities [Excel add-in]
- monitoring business activities [BAM], Excel add-in
ms.assetid: 305e3718-46b4-45df-bd52-f7ae36621576
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5702d1530926bf4bd0c2ecdc97520f777be3701e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385367"
---
# <a name="how-to-define-a-business-activity"></a>如何定义业务活动
若要指示您需要为报告收集的数据，必须定义 BAM 活动。 这包含一系列重要的里程碑和数据项您希望 BAM 跟踪。使用 BAM Excel 外接程序创建一个活动，如下面的过程中所示。  
  
> [!NOTE]
>  活动部署后，可在活动执行的操作就会受到限制。 具体而言，除非你已准备好让管理员取消部署整个 BAM 活动和视图集，然后重新部署它们，否则您不能从活动中删除项目。 除非管理员进行备份，这可能导致查看中断和数据丢失的数据和还原。  
  
### <a name="to-create-a-business-activity"></a>若要创建业务活动  
  
1.  打开 Microsoft Excel。  
  
2.  菜单在工具栏上，单击**BAM**菜单项，然后单击**BAM 活动**。  
  
     **业务活动监视活动向导**出现。  
  
3.  单击**新的活动**。  
  
     **新的活动**对话框随即出现。  
  
4.  键入一个描述性名称的活动**活动名称**文本框。  
  
> [!NOTE]
>  活动必须包含至少一个活动项。  
  
#### <a name="to-create-a-new-item"></a>若要创建新项  
  
1. 单击**新项**。  
  
2. 在中**新活动项**对话框中**新活动项**框中，键入活动项的描述性名称。  
  
3. 从**项类型**下拉列表菜单中，选择此项的类型。 可能的值包括：  
  
   |项类型|Description|  
   |---------------|-----------------|  
   |业务里程碑|日期/时间值。 例如，采购订单的批准日期。|  
   |业务数据 – Text|包含任何字母数字字符的字符串。 例如，发运到：城市、 省/市/自治区和邮政编码的代码。|  
   |业务数据 – Integer|一个整数值。 例如，购买的总数。|  
   |业务数据 – Decimal|一个十进制值。 有关示例的美元总金额的采购订单。|  
  
    如果您选择的项类型"业务数据 – Text"，则必须对字符串输入的最大字符数**的最大长度**框。  
  
   > [!NOTE]
   >  有关创建这些项的详细信息，请参阅"合作伙伴管理和业务活动监视"Microsoft BizTalk Server 教程中。  
  
4. 重复步骤 1 至 3，将添加到此活动所需的所有项。  
  
5. 完成业务活动监视活动向导后，业务活动监视视图向导将自动启动。  
  
   有关使用此向导的详细信息，请参阅[定义 BAM 视图](../core/defining-a-bam-view.md)。  
  
## <a name="see-also"></a>请参阅  
 [定义 BAM 视图](../core/defining-a-bam-view.md)   
 [在 Excel 中定义业务活动和视图](../core/defining-business-activities-and-views-in-excel.md)