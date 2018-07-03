---
title: 运行 Orchestrations2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- strong name keys, creating
- orchestrations
- creating strong name keys
- compiling orchestrations
- host instances, stopping and restarting
- deployment, orchestrations
- orchestrations, compiling
- orchestrations, deploying
- stopping host instances
- restarting host instances
ms.assetid: a098d552-d302-44f6-9af9-d77d16549fd3
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c299486c8ca43b34ba93ce434245b52b30e567aa
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981046"
---
# <a name="running-orchestrations"></a>运行业务流程
以下过程介绍如何生成、部署、绑定和启动业务流程。  
  
## <a name="creating-a-strong-name-key"></a>创建强名称密钥  
  
#### <a name="to-create-a-strong-name-key"></a>若要创建一个强名称密钥  
  
1. 打开[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]命令提示符。  
  
2. 将目录更改为指向现有的项目，然后按 ENTER 键。  
  
    例如：  
  
    **\<驱动器\>: \Adapter_Install\biztalk\my_project**  
  
3. 在命令提示符下键入以下命令并按 ENTER:  
  
    `sn -k SSOSchedule.snk`  
  
## <a name="compiling-and-deploying-an-orchestration"></a>编译和部署业务流程  
  
#### <a name="to-compile-and-deploy-an-orchestration"></a>若要编译和部署业务流程  
  
1. 在中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]解决方案资源管理器，右键单击**SSOSchedule**项目，并选择**属性**。  
  
2. 单击**常见属性**，然后展开**程序集**节点。  
  
3. 输入的路径中的 SSOSchedule.snk**程序集密钥文件**文本框。  
  
4. 验证配置 properties\deployment\server 是否是圆点 （.） 或您的计算机名称，然后单击**确定**。  
  
5. 在解决方案资源管理器中右键单击**SSOSchedule**，然后单击**重新生成**。  
  
6. 右键单击**SSOSchedule**，然后单击**部署**。  
  
## <a name="starting-the-orchestration"></a>启动业务流程  
  
#### <a name="to-start-the-orchestration"></a>若要启动的业务流程  
  
1. 单击**启动**，依次指向**所有程序**，指向**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**BizTalk Server 管理。**  
  
2. 在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，展开所需应用程序，，然后单击**业务流程**。  
  
3. 在详细信息窗格中，右键单击该业务流程，然后单击**启动**。  
  
## <a name="stopping-and-restarting-a-host-instance"></a>停止并重新启动主机实例  
 部署示例后，必须重新启动主机实例。  
  
#### <a name="to-stop-and-restart-a-host-instance"></a>若要停止并重新启动主机实例  
  
1. 单击**启动**，依次指向**所有程序**，指向**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**BizTalk Server 管理。**  
  
2. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**平台设置**，然后单击**主机实例**。  
  
3. 在右窗格中，右键单击主机实例 （例如，计算机名称），然后单击**停止**。  
  
    主机实例的状态将变为**已停止**。  
  
4. 在右窗格中，右键单击主机实例，然后单击**启动**。  
  
    主机实例的状态将变为**启动挂起**。  
  
    若要将状态更改为**运行**然后单击**刷新**，或右键单击主机实例，然后单击**刷新**。  
  
## <a name="see-also"></a>请参阅  
 [保护适配器](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)