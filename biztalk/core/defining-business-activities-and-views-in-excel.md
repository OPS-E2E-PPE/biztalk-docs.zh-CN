---
title: "在 Excel 中定义的业务活动和视图 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Excel add-in [BAM], creating business activities
- monitoring business activities [BAM], creating business activities
ms.assetid: 000532f0-cb9a-40ac-a6c5-a8bd4e49f8d0
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 91b9d3b213a6a6429759c0bb0d826798afa36da3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="defining-business-activities-and-views-in-excel"></a>在 Excel 中定义业务活动和视图
创建任何 BAM 解决方案的第一步都是确定感兴趣的数据以及如何解释这些数据。 为此，可使用适用于 Excel 的 BAM 外接程序。 使用该外接程序，可以通过定义业务活动来确定要使用的感兴趣数据的列表。 还可以定义数据的解释方式以及呈现给不同类别的业务用户时的显示方式。  
  
 使用 BAM 外接程序还可以定义聚合。  
  
 您还能够重命名活动项，例如，在某些用户熟悉的术语与活动中相应数据项的名称不匹配时需要重命名。 原因之一可能是视图的语言不同。  
  
 完成活动定义后，Excel 将生成随机预览数据，使用这些数据可以定义需要的图表和其他表示形式。 有关预览数据的详细信息，请参阅[如何使用数据透视表](../core/how-to-use-the-pivottable.md)。  
  
 完成的活动定义可定义业务流程运行过程中需要收集的数据点和事件。 您可以通过各种渠道获得 BAM 外接程序。  
  
 你可以安装在外接程序 XLA BAM[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装。 有关详细信息，请参阅[BizTalk Server 2013 和 2013 R2 的安装概述](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)  
  
 BAM。XLA 文件安装在以下位置之一：  
  
-   如果在计算机上未安装 Microsoft Office，则 BAM.xla 安装到 files\microsoft BizTalk Server 20*xx*\ExcelDir\ 文件夹。  
  
-   如果安装了 Microsoft Office，files\microsoft 网络中安装 BAM.xla*xx*\Library\ 文件夹。  
  
 还可以从其他计算机上的共享文件夹将 BAM.xla 复制到您的计算机。 然后通过从要复制到的位置选择它以便注册 XLA。  
  
 若要启用 BAM 外接程序 Excel 菜单工具栏上，单击**文件**菜单，然后单击**选项**，然后单击**外接程序**。选择**业务活动监视**，然后单击**转**，在 Ad 单元窗口中，选中的复选框旁边**业务活动监视**，然后单击**确定**。  
  
> [!NOTE]
>  使用 BAM 外接程序可避免两个正在运行的 Excel 实例被加载到同一进程中。  使用外接程序时，在以下情况下会在同一进程中出现多个实例：  
>   
>  打开一个 Excel 电子表格后，又启用了 BAM 外接程序，然后双击另一个 Excel 电子表格，Excel 会尝试将电子表格加载到当前正在运行的实例。  
>   
>  打开一个 Excel 电子表格后，又启用了 BAM 外接程序，这时使用“文件”/“打开”菜单选项加载另一个 Excel 电子表格。  
  
 在这种情况下，您不能正常使用外接程序。 若要在启用 BAM 外接程序的情况下打开多个 Excel 电子表格，必须先打开一个 Excel 的新副本，然后将电子表格加载到该 Excel 实例中。  
  
> [!NOTE]
>  当在 Excel 中使用 BAM.xla 时，你可能会收到错误"此工作簿已丢失其 VBA 项目，ActiveX 控件和任何其他可编程性相关的功能。" 有关错误的详细信息，请参阅[疑难解答 BAM](../core/troubleshooting-bam.md)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [如何定义业务活动](../core/how-to-define-a-business-activity.md)  
  
-   [定义 BAM 视图](../core/defining-a-bam-view.md)  
  
## <a name="see-also"></a>另请参阅  
 [监视与 BAM 业务活动](../core/monitoring-business-activities-with-bam.md)