---
title: "管理映射 |Microsoft 文档"
description: "若要使用 BizTalk Server 中，包括查看和删除映射中的映射的链接"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0e8e3057-5a9f-4b6b-b6ee-c71b7e6a51ac
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c86a1cd23fe8f06c2671be163409cd405e9cbe1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="manage-maps"></a>管理映射

## <a name="overview"></a>概述
本部分介绍如何使用 BizTalk Server 管理控制台来管理映射。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用地图翻译记录和记录的一个架构中的字段和另一个架构中的字段。 业务流程、发送端口和接收端口均可使用映射。  

## <a name="add-maps-to-an-application"></a>将地图添加到应用程序  
 地图内置的[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]和编译到 BizTalk 程序集中。 不能向应用程序中单独添加映射，而应按照以下方式向应用程序添加映射：  
  
-   中所述，添加包含映射到应用程序中，BizTalk 程序集的时[如何将 BizTalk 程序集添加到应用程序](../core/how-to-add-a-biztalk-assembly-to-an-application.md)。  
  
-   当你导入的应用程序中所述包括 BizTalk 程序集包含一个代码图，.msi 文件[如何导入 BizTalk 应用程序](../core/how-to-import-a-biztalk-application.md)。  
  
-   当开发人员将部署到应用程序包含中的地图的程序集[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]中所述，[部署 BizTalk 中的程序集到 BizTalk 应用程序的 Visual Studio](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)。  
  
 有关地图背景信息，请参阅[映射](../core/maps.md)。 有关创建映射的信息，请参阅[创建映射使用 BizTalk 映射程序](../core/creating-maps-using-biztalk-mapper.md)。  
  
> [!NOTE]
>  Microsoft Windows Management Instrumentation (WMI) 对象模型可用于创建和运行自动执行管理任务的脚本。 有关使用 WMI 的信息，请参阅**WMI 类引用** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
## <a name="next-steps"></a>后续步骤 
  
-   [应用程序中查看地图](../core/how-to-view-the-maps-for-an-application.md)  
  
-   [删除从应用程序的映射](../core/how-to-remove-a-map-from-an-application.md)