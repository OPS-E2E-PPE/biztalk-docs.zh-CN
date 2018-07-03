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
ms.openlocfilehash: 8c98ad06e902d06f2d24ac5f6fb01a2228753795
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006790"
---
# <a name="how-to-configure-a-strong-name-assembly-key-file"></a>如何配置强名称程序集密钥文件
在过程中部署 BizTalk 解决方案，[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]首先生成程序集。 部署过程要求每个程序集都是强签名的。 强可以通过将项目与一个强名称程序集密钥文件相关联来签名你的程序集。 如果你尚未这样做，则在从 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 部署某一解决方案之前，使用以下过程生成一个强名称程序集密钥文件并将它分配给解决方案中的每个项目。  
  
## <a name="prerequisites"></a>必要條件  
 若要执行本主题中的过程，你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators 组成员的帐户登录。 此外，你的帐户还必须对全局程序集缓存 (GAC) 具有写权限。 本地计算机的管理员帐户拥有此权限。  
  
### <a name="to-configure-a-strong-name-assembly-key-file"></a>配置强名称程序集密钥文件  
  
1. 启动**Visual Studio 命令提示符**。  
  
2. 在命令提示符下，从你要存储密钥文件的文件夹，键入以下命令，然后按 Enter 键：  
  
    **sn /k***file_name* **.snk**   
  
    示例： **sn /k ErrorHandling.snk**  
  
    一条确认消息，**密钥对写入** \< *file_name*\>**.snk** `,`显示命令行上。  
  
3. 在中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]解决方案资源管理器，右键单击项目，然后单击**属性**。  
  
4. 单击**签名**选项卡，选择**浏览**中**选择强名称密钥文件**下拉框。  
  
5. 浏览到密钥文件，然后单击该文件。 单击**打开**，然后关闭项目属性。  
  
6. 对解决方案中你要使用此强名称程序集密钥文件部署的每个项目，都重复步骤 3 到 6。  
  
## <a name="see-also"></a>请参阅  
 [将 BizTalk 程序集从 Visual Studio 部署到 BizTalk 应用程序](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)