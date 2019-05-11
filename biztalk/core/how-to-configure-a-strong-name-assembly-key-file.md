---
title: 如何配置强名称程序集密钥文件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5778a8ec-f5f7-4ae1-a57e-99f6503f044c
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce4dad74ae2b01684d7bd0650d8e1887af456e74
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386935"
---
# <a name="how-to-configure-a-strong-name-assembly-key-file"></a>如何配置强名称程序集密钥文件
在过程中部署 BizTalk 解决方案，[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]首先生成程序集。 部署过程要求每个程序集强签名。 强可以通过将项目与一个强名称程序集密钥文件相关联来签名你的程序集。 如果你尚未这样做，从部署解决方案之前[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，使用以下过程来生成强名称程序集密钥文件并将其分配到解决方案中每个项目。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，您必须登录的成员帐户[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员组。 此外，你的帐户必须在全局程序集缓存 (GAC) 具有写权限。 在本地计算机上的管理员帐户拥有此权限。  
  
### <a name="to-configure-a-strong-name-assembly-key-file"></a>若要配置强名称程序集密钥文件  
  
1. 启动**Visual Studio 命令提示符**。  
  
2. 在命令提示符下，从你想要存储密钥文件的文件夹键入以下命令，然后按 ENTER:  
  
    **sn /k**  *file_name* **.snk**  
  
    示例： **sn /k ErrorHandling.snk**  
  
    一条确认消息，**密钥对写入** \< *file_name*\>**.snk** `,`显示命令行上。  
  
3. 在中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]解决方案资源管理器，右键单击项目，然后单击**属性**。  
  
4. 单击**签名**选项卡，选择**浏览**中**选择强名称密钥文件**下拉框。  
  
5. 浏览到密钥文件并单击它。 单击**打开**，然后关闭项目属性。  
  
6. 你想要使用此强名称程序集密钥文件部署的解决方案中每个项目重复步骤 3 到 6。  
  
## <a name="see-also"></a>请参阅  
 [将 BizTalk 程序集从 Visual Studio 部署到 BizTalk 应用程序](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)