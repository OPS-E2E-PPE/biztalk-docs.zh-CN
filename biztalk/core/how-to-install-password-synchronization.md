---
title: 如何安装密码同步 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- installing, Password Synchronization [SSO]
- Password Synchronization [SSO], installing
ms.assetid: 8ace0401-b759-4ea3-91a0-be2aa8b5a5a4
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a3a6a3f93e600a8e68581f09af8fcdbc77ed57af
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25970931"
---
# <a name="how-to-install-password-synchronization"></a>如何安装密码同步
因为在默认的密码同步未安装单一登录与其他功能一起，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装，并且必须专门选择在安装过程。  
  
### <a name="to-install-password-synchronization"></a>安装密码同步  
  
1.  在 BizTalk Server 光盘，浏览到 **\<CDRoot\>\Platforms\SSO**文件夹。  
  
2.  运行**setup.exe**并按照向导中的说明。  
  
3.  选择**密码同步**功能并继续安装。  
  
 除此之外，还需要使用密码同步适配器才能发送和接收对外部系统的密码更改。 本部分中的主题将介绍如何配置您自己的适配器。  
  
 您也可以联系支持人员以获取有关可用的密码同步适配器的信息。  
  
 最后，若要捕获在 Active Directory 中所做的密码更改，则除了安装 ENTSSO 密码同步功能之外，还需在域控制器上安装组件才能捕获密码更改。  
  
 必须在要从中捕获密码的所有域控制器上安装 Windows 密码捕获组件和密码更改通知服务 (PCNS)。 您可以从以下位置安装这些组件：  
  
 [http://go.microsoft.com/fwlink/?LinkId=68145](http://go.microsoft.com/fwlink/?LinkId=68145)  
  
 在域控制器上继续进行安装之前，请阅读附带的文档（也位于此文件夹中）。  
  
## <a name="see-also"></a>另请参阅  
 [密码同步](../core/password-synchronization2.md)