---
title: 如何配置证书的参与方解析 |Microsoft 文档
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
ms.openlocfilehash: 153c8ccce1fafbe32c51b1c048fad4081f5b0b0b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22297717"
---
# <a name="how-to-configure-certificates-for-party-resolution"></a><span data-ttu-id="805fd-102">如何为参与方解析配置证书</span><span class="sxs-lookup"><span data-stu-id="805fd-102">How to Configure Certificates for Party Resolution</span></span>
<span data-ttu-id="805fd-103">当使用 BizTalk 资源管理器可配置方时，可以配置当事方，以便使用其数字签名解析方。</span><span class="sxs-lookup"><span data-stu-id="805fd-103">When you use BizTalk Explorer to configure a party, you can configure the party so that the party is resolved by using its digital signature.</span></span> <span data-ttu-id="805fd-104">如果这种方式，配置该参与方时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收消息时，它将使用的公钥证书，以确定谁发送邮件，并将解析发件人为中的已知方[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境。</span><span class="sxs-lookup"><span data-stu-id="805fd-104">If you configure the party this way, when [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receives a message, it will use the public key certificate to determine who sent the message, and to resolve the sender to a known party in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="805fd-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="805fd-105">Prerequisites</span></span>  
 <span data-ttu-id="805fd-106">若要执行本主题中的过程，你必须登录为的成员[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员组。</span><span class="sxs-lookup"><span data-stu-id="805fd-106">To perform the procedure in this topic, you must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-configure-party-resolution-to-use-a-certificate"></a><span data-ttu-id="805fd-107">若要配置为使用的证书的参与方解析</span><span class="sxs-lookup"><span data-stu-id="805fd-107">To configure party resolution to use a certificate</span></span>  
  
1.  <span data-ttu-id="805fd-108">打开**参与方属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="805fd-108">Open the **Party Properties** dialog box.</span></span>  
  
2.  <span data-ttu-id="805fd-109">单击**证书**选项卡上，并依次**浏览**。</span><span class="sxs-lookup"><span data-stu-id="805fd-109">Click the **Certificate** tab, and then click **Browse**.</span></span>  
  
3.  <span data-ttu-id="805fd-110">选择的证书。</span><span class="sxs-lookup"><span data-stu-id="805fd-110">Select a certificate.</span></span>  
  
4.  <span data-ttu-id="805fd-111">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="805fd-111">Click **OK**.</span></span>