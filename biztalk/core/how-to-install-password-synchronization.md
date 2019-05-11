---
title: 如何安装密码同步 |Microsoft Docs
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
ms.openlocfilehash: 7001dae85183069b5e977276582cceef91954db1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384926"
---
# <a name="how-to-install-password-synchronization"></a>如何安装密码同步
因为与其他单一登录功能，密码同步未安装在默认[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装，并且必须专门选择在安装过程。  
  
### <a name="to-install-password-synchronization"></a>若要安装密码同步  
  
1. 在 BizTalk Server CD 上浏览到 **\<CDRoot\>\Platforms\SSO**文件夹。  
  
2. 运行**setup.exe**并按照向导中的说明进行操作。  
  
3. 选择**密码同步**功能并继续进行安装。  
  
   除此之外，密码同步适配器都需要发送和接收到外部系统的密码更改。 在本部分中的主题介绍如何配置你自己的适配器。  
  
   您也可以联系支持人员以获取可用的密码同步适配器的信息。  
  
   最后，以捕获在 Active Directory 中，除了安装 ENTSSO 密码同步功能，所做的密码更改组件需要安装在要捕获的密码更改的域控制器上。  
  
   必须从中捕获密码的所有域控制器上安装的 Windows 密码捕获组件和密码更改通知服务 (PCNS)。 可以从以下位置安装这些组件：  
  
   [http://go.microsoft.com/fwlink/?LinkId=68145](http://go.microsoft.com/fwlink/?LinkId=68145)  
  
   阅读附带的文档 （也位于此文件夹） 之前进行域控制器上安装。  
  
## <a name="see-also"></a>请参阅  
 [密码同步](../core/password-synchronization2.md)