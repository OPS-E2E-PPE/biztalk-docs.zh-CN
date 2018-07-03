---
title: 步骤 1： 配置应用程序池标识 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message enrichment tutorial, application pools
- application pools
ms.assetid: 66286327-8580-4378-89ee-ddd7204b03c6
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 61cdbc019b2e36ea8c50d97ff03597374cb07253
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988486"
---
# <a name="step-1-configure-application-pool-identity"></a>步骤 1： 配置应用程序池标识
在本教程中，你可以使用应用程序池在 Microsoft Internet 信息服务 (IIS) 来处理业务流程发布为 Web 服务。 应用程序池是由工作进程提供服务的一个或多个 Url 的分组。  

 应用程序池标识是在其下运行的应用程序池辅助进程的服务帐户的名称。 默认情况下，应用程序池具有低级别的用户访问权限并且是本教程中对函数没有足够的网络服务用户帐户下运行。 出于安全原因，你想要配置应用程序池标识设置为用户帐户的绝对最低权限，但在最少的权限写入到 MessageBox (BizTalkMsgBoxDb) 数据库和配置数据库 (也称为 BizTalk管理数据库中，或 BizTalkMgmtDb）。  

### <a name="to-change-the-service-account-under-which-an-application-pool-runs"></a>若要更改的应用程序池中运行的服务帐户  

1. 单击**启动**，依次指向**程序**，指向**管理工具**，然后单击**Internet Information Services (IIS) Manager**.  

2. 在 Internet 信息服务 (IIS) 管理器中，展开本地计算机，然后展开**应用程序池**。  

3. 右键单击你想要配置的应用程序池 (默认情况下，在下运行此教程**DefaultAppPool**)，然后单击**属性**。  

4. DefaultAppPool 属性对话框中，在上**标识**选项卡上，执行以下操作：  


   |     使用此选项     |                                                                                                                                                                                                                                                                     执行的操作                                                                                                                                                                                                                                                                      |
   |------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |  **预定义的**  | 取消选中**预定义的**。 **预定义的**指的是标准的服务帐户，如下所示：<br /><br /> -   **网络服务**（默认值），其中包含可用于在远程计算机上的资源的访问权限的低级别的用户访问权限。<br />-   **本地服务**，具有低级别的访问权限。 对于不要求在远程计算机上的资源的访问权限的情况下使用此设置。<br />-   **本地系统**，这是使用 Network Service 或 Local Service 帐户之外的更多的用户权限的帐户。 |
   | **可配置** |                                                                                                                                                                                                                                     选择**可配置**。 **可配置**指的是已注册的用户名。                                                                                                                                                                                                                                      |
   |  **用户名**   |                                                                                                                                                                                                                                键入要在其下运行辅助进程的帐户的用户名。                                                                                                                                                                                                                                |
   |   **密码**   |                                                                                                                                                                                                                                                                 键入密码。                                                                                                                                                                                                                                                                  |


5. 单击“确定” 。  

   > [!NOTE]
   >  或者，为了提高安全性，可以创建在你创建具备定制为本教程的权限的自定义标识下运行的全新应用程序池。  

   请继续执行[步骤 2： 创建一个新项目](../../adapters-and-accelerators/accelerator-hl7/step-2-create-a-new-project.md)。  

## <a name="see-also"></a>请参阅  
 [消息充实教程](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)