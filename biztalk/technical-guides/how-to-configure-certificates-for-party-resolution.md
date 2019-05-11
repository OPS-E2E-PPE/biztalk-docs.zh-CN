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
# <a name="how-to-configure-certificates-for-party-resolution"></a><span data-ttu-id="0ecc0-102">如何为参与方解析配置证书</span><span class="sxs-lookup"><span data-stu-id="0ecc0-102">How to Configure Certificates for Party Resolution</span></span>
<span data-ttu-id="0ecc0-103">当您使用 BizTalk 浏览器中配置的参与方时，可以配置参与方，以便使用其数字签名解析的参与方。</span><span class="sxs-lookup"><span data-stu-id="0ecc0-103">When you use BizTalk Explorer to configure a party, you can configure the party so that the party is resolved by using its digital signature.</span></span> <span data-ttu-id="0ecc0-104">如果这样一来，配置参与方时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收消息时，它将使用的公钥证书确定谁发送的消息，并且将中的已知参与方解析发件人[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境。</span><span class="sxs-lookup"><span data-stu-id="0ecc0-104">If you configure the party this way, when [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receives a message, it will use the public key certificate to determine who sent the message, and to resolve the sender to a known party in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="0ecc0-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="0ecc0-105">Prerequisites</span></span>  
 <span data-ttu-id="0ecc0-106">若要执行本主题中的过程，您必须登录以成员的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。</span><span class="sxs-lookup"><span data-stu-id="0ecc0-106">To perform the procedure in this topic, you must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-configure-party-resolution-to-use-a-certificate"></a><span data-ttu-id="0ecc0-107">若要配置为使用的证书的参与方解析</span><span class="sxs-lookup"><span data-stu-id="0ecc0-107">To configure party resolution to use a certificate</span></span>  
  
1.  <span data-ttu-id="0ecc0-108">打开**参与方属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="0ecc0-108">Open the **Party Properties** dialog box.</span></span>  
  
2.  <span data-ttu-id="0ecc0-109">单击**证书**选项卡，然后依次**浏览**。</span><span class="sxs-lookup"><span data-stu-id="0ecc0-109">Click the **Certificate** tab, and then click **Browse**.</span></span>  
  
3.  <span data-ttu-id="0ecc0-110">选择一个证书。</span><span class="sxs-lookup"><span data-stu-id="0ecc0-110">Select a certificate.</span></span>  
  
4.  <span data-ttu-id="0ecc0-111">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="0ecc0-111">Click **OK**.</span></span>