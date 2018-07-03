---
title: 管理映射 |Microsoft Docs
description: 若要使用 BizTalk Server，其中包括查看和删除映射中的映射的链接
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0e8e3057-5a9f-4b6b-b6ee-c71b7e6a51ac
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d6957a4f3d73c5f59df5cd36f70a7ed34631fa6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37019827"
---
# <a name="manage-maps"></a>管理映射

## <a name="overview"></a>概述
本部分介绍如何使用 BizTalk Server 管理控制台来管理映射。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用映射转换的记录和记录的一个架构中的字段和另一个架构中的字段。 业务流程、发送端口和接收端口均可使用映射。  

## <a name="add-maps-to-an-application"></a>将地图添加到应用程序  
 映射内置的[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]并编译到 BizTalk 程序集。 不能向应用程序中单独添加映射，而应按照以下方式向应用程序添加映射：  
  
- 添加 BizTalk 程序集包含映射到该应用程序，如中所述[如何将 BizTalk 程序集添加到应用程序](../core/how-to-add-a-biztalk-assembly-to-an-application.md)。  
  
- 某一.msi 文件导入包含其中包含的映射的 BizTalk 程序集，如中所述的应用程序[导入 BizTalk 应用程序的方式](../core/how-to-import-a-biztalk-application.md)。  
  
- 当开发人员部署到应用程序包含从映射的程序集[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，如中所述[从到 BizTalk 应用程序的 Visual Studio 部署 BizTalk 程序集](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)。  
  
  有关地图的背景信息，请参阅[映射](../core/maps.md)。 有关创建映射的信息，请参阅[创建映射使用 BizTalk 映射器](../core/creating-maps-using-biztalk-mapper.md)。  
  
> [!NOTE]
>  Microsoft Windows Management Instrumentation (WMI) 对象模型可用于创建和运行自动执行管理任务的脚本。 有关使用 WMI 的信息，请参阅**WMI 类引用** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
## <a name="next-steps"></a>后续步骤 
  
-   [查看应用程序映射](../core/how-to-view-the-maps-for-an-application.md)  
  
-   [从应用程序中删除映射](../core/how-to-remove-a-map-from-an-application.md)