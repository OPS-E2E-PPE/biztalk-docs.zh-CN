---
title: "如何配置证书的参与方解析 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 060101c1-14f3-4600-a18e-48a160d59bca
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 153c8ccce1fafbe32c51b1c048fad4081f5b0b0b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-certificates-for-party-resolution"></a>如何为参与方解析配置证书
当使用 BizTalk 资源管理器可配置方时，可以配置当事方，以便使用其数字签名解析方。 如果这种方式，配置该参与方时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收消息时，它将使用的公钥证书，以确定谁发送邮件，并将解析发件人为中的已知方[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，你必须登录为的成员[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员组。  
  
### <a name="to-configure-party-resolution-to-use-a-certificate"></a>若要配置为使用的证书的参与方解析  
  
1.  打开**参与方属性**对话框。  
  
2.  单击**证书**选项卡上，并依次**浏览**。  
  
3.  选择的证书。  
  
4.  单击 **“确定”**。