---
title: 如何还原证书存储 |Microsoft Docs
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
ms.openlocfilehash: 22a31c1b1fb9c25050202aa4f5f69fcd39af424b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384095"
---
# <a name="how-to-restore-the-certificate-store"></a>如何还原证书存储
作为恢复的一部分[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，必须还原证书存储区。 如果要恢复[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Standard Edition 中，您必须使用此过程来还原证书存储。 不需要执行此过程恢复的所有其他版本时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]因为恢复过程将自动还原你的证书存储区。  
  
## <a name="prerequisites"></a>先决条件  
 您必须为要执行此过程的管理员组的成员身份登录。  
  
### <a name="to-restore-the-certificate-store-biztalk-server-standard-edition"></a>若要还原证书存储 （BizTalk Server 标准版）  
  
1.  单击**启动**，单击**所有程序**，然后单击**Internet Explorer**。  
  
2.  上**工具**菜单上，单击**Internet 选项**。  
  
3.  在中**Internet 选项**对话框中，单击**内容**选项卡，然后依次**证书**。  
  
4.  在中**证书**对话框中，单击**其他人**选项卡，然后依次**导入**。  
  
5.  在中**证书导入向导**，单击**取消**。  
  
     这将创建**通讯簿**注册表中的 hive。  
  
6.  在中**证书**对话框中，单击**关闭**。  
  
7.  在中**Internet 选项**对话框中，单击**确定**。  
  
8.  单击**文件**，然后单击**关闭**退出 Internet Explorer。  
  
9. 单击**启动**，单击**运行**，类型**regedit**，然后单击**确定**。  
  
10. 在注册表编辑器中，导航到以下注册表项：  
  
     **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\SystemCertificates**  
  
11. 确认**通讯簿**配置单元是否存在。  
  
## <a name="see-also"></a>请参阅  
 [恢复运行 BizTalk Server 的计算机](../core/recovering-a-computer-running-biztalk-server.md)