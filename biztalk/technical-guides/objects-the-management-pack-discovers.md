---
title: 对象的管理包可发现 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 291e8936-b299-4719-9f7e-edc86f76fcbd
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c5c96ea4b2d1b54dfd6105c40046810fb6482e92
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990598"
---
# <a name="objects-the-management-pack-discovers"></a>管理包发现的对象
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理包可发现下表中所述的对象类型。 有关发现对象的信息，请参阅[Operations Manager 2007 中的对象发现](http://go.microsoft.com/fwlink/?LinkId=108505)Operations Manager 2007 R2/2012年联机库中的主题 (<http://go.microsoft.com/fwlink/?LinkId=108505>)。  
  
|“属性”|类别|对象类型|  
|----------|--------------|-----------------|  
|BizTalkGroup|逻辑实体|应用程序视图对象|  
|BizTalkHost|逻辑实体|应用程序视图对象|  
|BizTalkApplication|逻辑实体|应用程序视图对象|  
|ApplicationArtifact|逻辑实体|应用程序视图对象|  
|HostedApplicationArtifact|逻辑实体|应用程序视图对象|  
|接收端口|应用程序项目|应用程序视图对象|  
|ReceiveLocation|应用程序项目|应用程序视图对象|  
|业务流程|应用程序项目|应用程序视图对象|  
|发送端口|应用程序项目|应用程序视图对象|  
|发送端口组|应用程序项目|应用程序视图对象|  
|BizTalkGroupDeployment|System.Service|部署视图对象|  
|BizTalkInstallation|Windows.SoftwareInstallation|部署视图对象|  
|ServerRole|Windows.ComputerRole|部署视图对象|  
|BiztalkRuntimeRole|ServerRole|部署视图对象|  
|RulesEngineRole|BizTalkServerRole|部署视图对象|  
|BAMRole|逻辑实体|部署视图对象|  
|BAMRuntime|逻辑实体|部署视图对象|  
|BAMAnalysis|逻辑实体|部署视图对象|  
|BAMAlerts|逻辑实体|部署视图对象|  
|BAMPortal|网站 (Web site)|部署视图对象|  
|BizTalkApplicationService|Windows.ApplicationComponent|部署视图对象|  
|BizTalkHostDeployment|逻辑实体|部署视图对象|