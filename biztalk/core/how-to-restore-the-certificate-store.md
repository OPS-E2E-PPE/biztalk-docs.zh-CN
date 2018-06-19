---
title: 如何还原证书存储区 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0c6f7551-d119-4668-9b52-6013f69a0302
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aaeee6b762cf5af15ca7cba34864abd86682d4df
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254693"
---
# <a name="how-to-restore-the-certificate-store"></a>如何还原证书存储
在恢复 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的过程中，必须还原证书存储。 如果要恢复 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 标准版，则必须使用此过程来还原证书存储。 在恢复 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的所有其他版本时，不需要执行此过程，因为恢复过程将自动为您还原证书存储。  
  
## <a name="prerequisites"></a>先决条件  
 必须以 Administrators 组成员的身份登录，才能执行此过程。  
  
### <a name="to-restore-the-certificate-store-biztalk-server-standard-edition"></a>还原证书存储（BizTalk Server 标准版）  
  
1.  单击**启动**，单击**所有程序**，然后单击**Internet Explorer**。  
  
2.  上**工具**菜单上，单击**Internet 选项**。  
  
3.  在**Internet 选项**对话框中，单击**内容**选项卡上，并依次**证书**。  
  
4.  在**证书**对话框中，单击**其他人**选项卡上，并依次**导入**。  
  
5.  在**证书导入向导**，单击**取消**。  
  
     这将创建**通讯簿**注册表中的 hive。  
  
6.  在**证书**对话框中，单击**关闭**。  
  
7.  在**Internet 选项**对话框中，单击**确定**。  
  
8.  单击**文件**，然后单击**关闭**退出 Internet Explorer。  
  
9. 单击**启动**，单击**运行**，类型**regedit**，然后单击**确定**。  
  
10. 在注册表编辑器中，导航到以下注册表项：  
  
     **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\SystemCertificates**  
  
11. 验证**通讯簿**配置单元已存在。  
  
## <a name="see-also"></a>另请参阅  
 [恢复运行 BizTalk Server 的计算机](../core/recovering-a-computer-running-biztalk-server.md)