---
title: 如何查看 BAM 聚合 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- aggregations [BAM], viewing aggregations
- viewing, aggregations [BAM]
ms.assetid: aa697f16-ac47-46f9-98a5-a951961d0413
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2b1bc81ac4cc85cdb2f9d02903b9c9ba0f3ef7c3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22256661"
---
# <a name="how-to-view-bam-aggregations"></a>如何查看 BAM 聚合
BAM 聚合是由业务分析员在 Excel 中使用 Excel 外接程序定义的。  
  
### <a name="to-view-your-bam-aggregations"></a>查看您的 BAM 聚合  
  
1.  在运行的计算机上[!INCLUDE[btsPlatformsComApis](../includes/btsplatformscomapis-md.md)]; 单击**启动**，指向**所有程序**，右键单击**Internet Explorer**，然后单击**以运行管理员**。 在**用户帐户控制**对话框中，单击**继续**。 在 Internet Explorer 地址栏中，键入`http://<server>/BAM/`，其中*\<服务器 >* 是运行 BAM 门户的计算机的名称。  
  
     --或者--  
  
     单击**启动**，单击**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BAM 门户网站**。  
  
2.  从**MyViews**导航窗格中，单击一个视图，以展开的视图以显示任务列表。  
  
3.  单击**聚合**任务以展开的列表定义聚合。  
  
4.  单击列出加载 BAM 门户内容的帧中的聚合的聚合。  
  
> [!NOTE]
>  如果没有显示任何视图，则是因为视图尚未创建（此任务通常由业务分析员执行），或尚未向用户授予权限（此任务通常由管理员执行）。  
  
 有关如何使用实时数据工作簿的详细信息，请参阅[查看实时 BAM 数据](../core/viewing-live-bam-data.md)。  
  
 下图显示了预先计算的 BAM 聚合。  
  
 ![](../core/media/bam-olap-cube.gif "bam_olap_cube")  
预先计算的 BAM 聚合