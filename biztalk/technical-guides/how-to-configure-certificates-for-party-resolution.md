---
title: 如何为参与方解析配置证书 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 060101c1-14f3-4600-a18e-48a160d59bca
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ad5a25799599c668011e9ef2e322a016f649b198
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65253498"
---
# <a name="how-to-configure-certificates-for-party-resolution"></a>如何为参与方解析配置证书
当您使用 BizTalk 浏览器中配置的参与方时，可以配置参与方，以便使用其数字签名解析的参与方。 如果这样一来，配置参与方时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收消息时，它将使用的公钥证书确定谁发送的消息，并且将中的已知参与方解析发件人[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，您必须登录以成员的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。  
  
### <a name="to-configure-party-resolution-to-use-a-certificate"></a>若要配置为使用的证书的参与方解析  
  
1.  打开**参与方属性**对话框。  
  
2.  单击**证书**选项卡，然后依次**浏览**。  
  
3.  选择一个证书。  
  
4.  单击“确定” 。