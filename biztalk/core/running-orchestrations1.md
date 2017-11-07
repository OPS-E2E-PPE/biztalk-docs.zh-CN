---
title: "运行 Orchestrations1 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- strong name keys, creating
- orchestrations
- host instances, stopping and restarting
- orchestrations, compiling
- orchestrations, deploying
ms.assetid: b992bdba-630d-4f28-aca8-c568f3c27968
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b4559a3d362d0d778c4d60cc485fa79e8e05efe
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
---
# <a name="running-orchestrations"></a>运行业务流程
以下过程介绍如何生成、部署、绑定和启动业务流程。  
  
## <a name="creating-a-strong-name-key"></a>创建强名称密钥  
  
#### <a name="to-create-a-strong-name-key"></a>若要创建强名称密钥  
  
1.  启动 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 命令提示符。  
  
2.  例如，将目录更改为现有项目中，\<驱动器 >: \Adapter_Install\biztalk2010\my_project。  
  
3.  在命令提示符中键入以下内容并按 Enter：  
  
     `sn -k SSOSchedule.snk`  
  
## <a name="compiling-and-deploying-an-orchestration"></a>编译和部署业务流程  
  
#### <a name="to-compile-and-deploy-an-orchestration"></a>若要编译并部署业务流程  
  
1.  在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]解决方案资源管理器，右键单击 SSOSchedule 项目，然后选择**属性**。  
  
2.  单击**通用属性**，然后展开**程序集**节点。  
  
3.  输入的路径中的 SSOSchedule.snk**程序集密钥文件**文本框。  
  
4.  验证配置 Properties\Deployment\Server 包含句点 （.） 或你计算机的名称，然后单击**确定**。  
  
5.  在解决方案资源管理器，右键单击**SSOSchedule**，然后单击**重新生成**。  
  
6.  右键单击**SSOSchedule**，然后单击**部署**。  
  
## <a name="starting-the-orchestration"></a>启动业务流程  
  
#### <a name="to-start-the-orchestration"></a>若要启动业务流程  
  
1.  在 BizTalk 管理控制台中，选择要启动的业务流程。  
  
2.  右键单击业务流程和单击**启动**。  
  
## <a name="stopping-and-restarting-a-host-instance"></a>停止并重新启动主机实例  
 部署示例后，必须重新启动主机实例。  
  
#### <a name="to-stop-and-restart-a-host-instance"></a>若要停止并重新启动主机实例  
  
1.  单击**启动**，指向**所有程序**，指向**Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]，然后选择**BizTalk Server 管理。**  
  
2.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，双击**Microsoft BizTalk Server （本地）**节点，然后展开**主机**。  
  
3.  在左窗格中，选择**BizTalkServerApplication**。  
  
4.  在右窗格中，右键单击主机实例 （例如，计算机名称），然后单击**停止**。  
  
     主机实例的状态更改为**已停止**。  
  
5.  在右窗格中，右键单击主机实例，然后单击**启动**。  
  
     主机实例的状态更改为**启动挂起**。  
  
     若要将状态更改为**运行**，单击**刷新**，或右键单击主机实例，然后单击**刷新**。  
  
## <a name="see-also"></a>另请参阅  
 [适配器中的安全](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)