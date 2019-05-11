---
title: 在 Excel 中定义业务活动和视图 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Excel add-in [BAM], creating business activities
- monitoring business activities [BAM], creating business activities
ms.assetid: 000532f0-cb9a-40ac-a6c5-a8bd4e49f8d0
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1516cab2ac18000fd010bf48fcc140512b67dffc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390290"
---
# <a name="defining-business-activities-and-views-in-excel"></a>在 Excel 中定义业务活动和视图
创建任何 BAM 解决方案的第一步是确定感兴趣的哪些数据以及应如何解释这些数据。 若要执行此操作，您使用 BAM 外接程序 excel。 外接程序，可通过定义业务活动来定义所需的数据的愿望。 此外可以为不同类别的业务用户定义数据的解释方式以及所示的方式。  
  
 BAM 外接程序还可以定义聚合。  
  
 此外可以重命名活动项，例如，其中，某些用户熟悉的术语与活动中的相应数据项的名称不匹配。 有关这一种解释是视图所在不同的语言。  
  
 完成活动定义后，Excel 将生成随机预览数据，可用于定义所需的图表和其他表示形式。 有关预览数据的详细信息，请参阅[如何使用该数据透视表](../core/how-to-use-the-pivottable.md)。  
  
 已完成的活动定义用于定义数据点和业务流程运行时收集所需的事件。 可以从各种源获取 BAM 外接程序。  
  
 你可以安装在过程外接程序 XLA BAM[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装。 有关详细信息，请参阅[BizTalk Server 2013 和 2013 R2 安装概述](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)  
  
 BAM。XLA 文件安装在以下位置之一：  
  
- 如果在计算机上未安装 Microsoft Office，则将 BAM.xla 安装到 files\microsoft BizTalk Server 20*xx*\ExcelDir\ 文件夹。  
  
- 如果安装 Microsoft Office，则将 BAM.xla 安装中 \Program Files\Microsoft 网络*xx*\Library\ 文件夹。  
  
  此外可以从另一台计算机上的共享文件夹到您的计算机复制将 BAM.xla。 然后可以通过从复制到其中的位置选择它来注册 XLA。  
  
  若要启用 BAM 外接程序在 Excel 菜单工具栏上，单击**文件**菜单，然后单击**选项**，然后单击**外接程序**。选择**业务活动监视**，然后单击**转**，在 Ad 接窗口中，选中复选框旁边**业务活动监视**，然后单击**确定**。  
  
> [!NOTE]
>  使用 BAM 外接程序，不能包含两个实例加载到同一进程中运行 Excel。  当使用外接程序，在同一进程中的多个实例可能会发生以下情况下：  
>   
>  具有的 Excel 电子表格打开与 BAM 外接程序启用时，并双击不同的 Excel 电子表格，Excel 尝试将电子表格加载到当前正在运行的实例。  
>   
>  Excel 电子表格打开后，使用 BAM 外接程序已启用，并使用文件 / 打开菜单选项加载另一个 Excel 电子表格。  
  
 您不能使用外接程序正确地在这种情况下。 若要打开多个 Excel 电子表格具有 BAM 外接程序启用时，必须打开 Excel 的新副本并将电子表格加载到该 Excel 实例。  
  
> [!NOTE]
>  在 Excel 中使用 BAM.xla 时，你可能会收到错误"此工作簿已丢失了其 VBA 项目、 ActiveX 控件和任何其他与可编程序相关的功能。" 有关错误的详细信息，请参阅[故障排除 BAM](../core/troubleshooting-bam.md)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [如何定义业务活动](../core/how-to-define-a-business-activity.md)  
  
-   [定义 BAM 视图](../core/defining-a-bam-view.md)  
  
## <a name="see-also"></a>请参阅  
 [使用 BAM 监视业务活动](../core/monitoring-business-activities-with-bam.md)