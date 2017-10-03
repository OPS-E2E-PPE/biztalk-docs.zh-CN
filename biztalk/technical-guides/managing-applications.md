---
title: "管理应用程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ef1039fb-7460-444b-a45e-2783bdc7c109
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 52e525499671a04228763c6792961c3204a3a2d2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="managing-applications"></a>管理应用程序
BizTalk 应用程序是应用程序项目，比如业务流程、 管道、 架构、 映射和端口的逻辑容器。 BizTalk 应用程序，可以将相关的组件包括在同一个容器。 应用程序中的任何项目可以引用到该应用程序中的任何其他项目或在任何被引用的应用程序中的任何项目。 可以在 BizTalk 应用程序中的项目的完整列表，请参阅[BizTalk 应用程序是什么？](http://go.microsoft.com/fwlink/?LinkId=154994) (http://go.microsoft.com/fwlink/?LinkId=154994)。  
  
 BizTalk 应用程序简化许多每天[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]任务。 可以部署、 管理、 启动、 停止和故障排除[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序级别。 这会导致的混淆和针对用户错误的风险更低。 BizTalk 应用程序容器包含  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]由 Visual Studio 环境部署到它的程序集。 应用程序还可能包含接收端口、 接收位置、 发送端口、 属性的跟踪设置，和角色的链接。 也可以手动添加[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]程序集的应用程序或移动到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]从其他应用程序的程序集。 此外，你可以添加非[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]程序集和[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]如业务规则引擎 (BRE) 策略和 BAM 定义文件的项目。 隐式应用程序将还包含的所有绑定都由它们的当前设置。  
  
 你可以创建预或后续处理脚本来执行操作，导入应用程序时，安装或卸载。 有关使用此类脚本的详细信息，请参阅[使用自定义应用程序部署到的前期和后期处理脚本](http://go.microsoft.com/fwlink/?LinkId=154995)(http://go.microsoft.com/fwlink/?LinkId=154995)。  
  
 本部分介绍如何部署，版本，并更新应用程序或单个项目。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [部署应用程序](../technical-guides/deploying-an-application.md)  
  
-   [更新应用程序](../technical-guides/updating-an-application.md)