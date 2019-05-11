---
title: 使用 MQSAgent COM + 配置向导 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.mqsagent.wizard
helpviewer_keywords:
- MQSeries adapters, MQSAgent COM+ Configuration Wizard
- configuring [MQSeries adapters], MQSAgent COM+ Configuration Wizard
- MQSAgent COM+ Configuration Wizard
ms.assetid: f106700a-7f57-4c83-9344-6525fc10544d
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f304039d0d6d68d12bfc7605cba69bb01e22ca7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395993"
---
# <a name="using-the-mqsagent-com-configuration-wizard"></a>使用 MQSAgent COM + 配置向导
MQSAgent COM + 配置向导配置 MQSAgent COM + 应用程序 （MQSeries 组件） 适配器的部分。 该向导设置组件的角色名称和用户角色中包含的应用程序标识。 使用 MQSAgent COM + 配置向导创建的 MQSAgent COM + 组件的名称是**MQSAgent2**。  

> [!NOTE]
>  64 位 Windows server 支持 MQSAgent COM + 应用程序。 它将作为 32 位进程在 WOW64 下运行。 一个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]-64 位版本的 Windows Server 运行的基于的计算机可以与安装有 MQSAgent 的远程 32 位计算机进行通信。  
> 
> [!NOTE]
>  MQSeries 代理和 MQSAgent COM + 配置向导可执行文件**MQSConfigWiz.exe**如果从 BizTalk Server 2009 升级到 BizTalk Server 将不会安装。 从 BizTalk Server 2009 重新运行安装程序升级到 BizTalk Server，然后选择**修改**选项，然后选择 MQSeries 代理下要安装这些组件的其他软件。  

## <a name="to-set-the-application-identity"></a>若要设置应用程序标识  

-   使用**应用程序标识**MQSAgent COM + 配置向导，如下所示设置 mqsagent 的应用程序标识的页：  

    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**交互式用户**|选择此选项可将当前的登录帐户用于应用程序标识。|  
    |**Local Service**|设置应用程序标识为内置服务帐户。|  
    |**Network Service**|设置应用程序标识为具有网络访问权限的内置帐户。|  
    |**此用户**|将应用程序标识设置为指定的用户名。|  

> [!NOTE]
>  不建议你使用帐户具有管理权限的应用程序标识。 该帐户必须具有所需的最小权限： 读取和写入 MQSeries 队列的权限。  

## <a name="to-name-the-role-and-add-users-to-it"></a>若要命名角色并向其添加用户  

- 使用**名称的角色**MQSAgent COM + 配置向导，如下所示将名称和用户分配到角色页：  


  |     使用此选项     |                                                                         执行的操作                                                                          |
  |------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------|
  | **角色的名称** |                                                                 键入角色的名称。                                                                  |
  |    **用户**     |                                                         显示属于该角色的用户。                                                          |
  |     **“添加”**      | 将用户添加到角色。 这些是[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]服务帐户使用的适配器。 |

> [!NOTE]
>  将添加到需要访问适配器的角色唯一帐户。  

## <a name="to-set-the-msdtc-security-configuration-on-the-windows-server-2008-computer-to-no-authentication-required"></a>若要在不要求进行身份验证的 Windows Server 2008 计算机上设置的 MSDTC 安全配置  
 如果在安装了 MQSAgent COM + 应用程序[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]上安装了计算机和 MQSeries 适配器 （这与 BizTalk Server 一起安装）[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]或[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]计算机、 上的 MSDTC 安全配置[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]或[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]计算机必须设置为**不要求进行身份验证**。 请按照下列步骤将 MSDTC 安全配置设置为不要求进行验证：  

1.  单击**启动**，然后单击**控制面板**。  

2.  双击**管理工具**。  

3.  双击**组件服务**以启动**组件服务**管理界面。  

4.  展开**组件服务**，展开**计算机**，然后展开**我的电脑**。  

5.  右键单击**我的电脑**然后单击**属性**菜单项。  

6.  在中**我的电脑**对话框中，单击**MSDTC**选项卡，然后单击**安全配置**。  

7.  在中**的安全配置**对话框中**事务管理器通信**部分中，选择**不要求进行身份验证**。 如果系统提示您在对话框中，单击**是**以重新启动 MS DTC 服务。  

8.  重新启动 MS DTC 服务后，单击**确定**然后单击**确定**以关闭**我的电脑**对话框。  

9. 关闭**组件服务**管理界面。  

## <a name="to-configure-the-mqsagent-runtime-components-to-run-under-an-alternative-set-of-credentials"></a>若要配置 MQSAgent 运行时组件，另一组凭据下运行  
 MQSAgent COM + 应用程序包括用于管理和运行时组件。 如果你想要此功能分隔到不同 COM + 应用程序出于安全目的，在安装了 MQSAgent COM + 应用程序的计算机上执行以下步骤：  

1.  启用 MQSAgent COM + 组件的更改。  

    -   单击**启动**，然后单击**控制面板**。  

    -   双击**管理工具**。  

    -   双击**组件服务**以启动**组件服务**管理界面。  

    -   展开**组件服务**，展开**我的电脑**，展开**COM + 应用程序**，右键单击**MQSAgent2** COM + 应用程序然后单击**属性**。  

    -   单击**高级**选项卡上，取消选中**禁用更改**。  

    -   单击“确定” 。  

2.  创建一个新 COM + 应用程序为 MQSAgent 运行时组件。  

    -   右键单击**COM + 应用程序**，单击**新建**，**应用程序**以显示**COM + 应用程序安装向导**单击**下一步**。  

    -   单击**创建一个空应用程序**。  

    -   输入的名称**MQSAgent2RunTime**，请保留为默认选项**服务器应用程序**启用，然后单击**下一步**。  

    -   选择的选项**此用户**，输入相应的帐户信息，然后单击**下一步**。  

        > [!NOTE]
        >  此帐户应具有**连接**并**放置**和/或**获取**上相应的 IBM WebSphere MQ Windows 队列的权限。 可以设置此帐户具有适当的权限**setmqaut**与 IBM WebSphere MQ 可用命令。 有关详细信息**setmqaut**命令，请参阅 IBM WebSphere MQ 文档。  

    -   单击**下一步**上**添加应用程序角色**对话框。  

    -   单击**下一步**上**向角色添加用户**对话框。  

    -   单击 **“完成”**。  

3.  将运行时组件移至新的 COM + 应用程序  

    -   展开**MQSAgent2** COM + 应用程序。  

    -   展开**组件**。  

    -   右键单击**MQSAgent2.MQSAgent.1**组件，然后单击**移动**以显示**移动组件 (s)** 对话框。  

    -   选择**MQSAgent2RunTime**下**请选择一个目标**然后单击**确定**。  

    -   重复这些步骤**MQSAgent2.MQSBroker.1**并**MQSAgent2.MQSProxy.1**组件。  

## <a name="see-also"></a>请参阅  
 [如何配置 MQSeries 适配器发送和接收处理程序](../core/how-to-configure-mqseries-adapter-send-and-receive-handlers.md)   
 [配置 MQSeries 适配器](../core/configuring-the-mqseries-adapter.md)