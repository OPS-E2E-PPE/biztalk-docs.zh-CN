---
title: 配置签名证书 (AS2) |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8539e210-1656-4fff-b026-36b81689061f
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 32a52962976c2db62de902906f53f5c270e2c7c0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233261"
---
# <a name="configuring-signature-certificates-as2"></a><span data-ttu-id="ea791-102">配置签名证书（AS2）</span><span class="sxs-lookup"><span data-stu-id="ea791-102">Configuring Signature Certificates (AS2)</span></span>
<span data-ttu-id="ea791-103">作为此页上设置的一部分，您可以指定用于签署所有传出消息的证书和用于解析此协议的 MDN。</span><span class="sxs-lookup"><span data-stu-id="ea791-103">As part of the settings on this page, you can specify the certificates to be used for signing all outgoing messages and MDN that resolve to this agreement.</span></span> <span data-ttu-id="ea791-104">此页上的设置将覆盖作为 BizTalk 组属性一部分提供的证书设置。</span><span class="sxs-lookup"><span data-stu-id="ea791-104">The settings on this page override the certificate settings provided as part of the BizTalk Group properties.</span></span> <span data-ttu-id="ea791-105">有关证书的使用方式的详细信息，请参阅[Configuring certificates for AS2 证书](../core/configuring-certificates-for-as2.md)。</span><span class="sxs-lookup"><span data-stu-id="ea791-105">For more information on how certificates are used, see [Configuring Certificates for AS2](../core/configuring-certificates-for-as2.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ea791-106">没有属性禁用此页上，即使你清除**本地 BizTalk 处理接收方或支持从该参与方发送消息的消息**时正在创建你为其创建参与方的复选框协议。</span><span class="sxs-lookup"><span data-stu-id="ea791-106">No properties are disabled on this page even if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ea791-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="ea791-107">Prerequisites</span></span>  
 <span data-ttu-id="ea791-108">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="ea791-108">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-agreement-level-signature-certificate"></a><span data-ttu-id="ea791-109">配置协议层签名证书</span><span class="sxs-lookup"><span data-stu-id="ea791-109">To configure agreement-level signature certificate</span></span>  
  
1.  <span data-ttu-id="ea791-110">创建 AS2 协议中所述[配置常规设置 (AS2)](../core/configuring-general-settings-as2.md)。</span><span class="sxs-lookup"><span data-stu-id="ea791-110">Create an AS2 agreement as described in [Configuring General Settings (AS2)](../core/configuring-general-settings-as2.md).</span></span> <span data-ttu-id="ea791-111">若要更新现有 AS2 协议，右键单击在协议**方和业务配置文件**页，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="ea791-111">To update an existing AS2 agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="ea791-112">单向协议选项卡上，单击**签名证书**。</span><span class="sxs-lookup"><span data-stu-id="ea791-112">On a one-way agreement tab, click **Signature Certificates**.</span></span>  
  
3.  <span data-ttu-id="ea791-113">选择**覆盖组签名证书**复选框以使用此页中提供用于对传出的 AS2 消息和 MDN 签名的证书。</span><span class="sxs-lookup"><span data-stu-id="ea791-113">Select the **Override group signing certificate** check box to use the certificate provided in this page for signing outgoing AS2 messages and MDN.</span></span>  
  
4.  <span data-ttu-id="ea791-114">单击**浏览**以显示**选择证书**对话框中，你在其中选择要应用于此方传输的消息的签名证书。</span><span class="sxs-lookup"><span data-stu-id="ea791-114">Click **Browse** to display the **Select Certificate** dialog box, where you select the signature certificate to apply to messages transmitted by this party.</span></span>  
  
5.  <span data-ttu-id="ea791-115">**公用名**文本框中显示所选证书的说明。</span><span class="sxs-lookup"><span data-stu-id="ea791-115">The **Common Name** text box displays a description of the selected certificate.</span></span>  
  
6.  <span data-ttu-id="ea791-116">**指纹**文本框中显示证书的指纹。</span><span class="sxs-lookup"><span data-stu-id="ea791-116">The **Thumbprint** text box displays the thumbprint of certificate.</span></span> <span data-ttu-id="ea791-117">证书指纹的格式 HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH，其中 H 是十六进制数字 （介于 0 到 9） 或从 A 到 F 字母。</span><span class="sxs-lookup"><span data-stu-id="ea791-117">The certificate thumbprint has the format HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH, where H is a hexadecimal digit (a number from 0 through 9 or a letter from A through F).</span></span>  
  
7.  <span data-ttu-id="ea791-118">单击**删除证书**若要删除所选的证书。</span><span class="sxs-lookup"><span data-stu-id="ea791-118">Click **Remove Certificate** to remove the selected certificate.</span></span>  
  
8.  <span data-ttu-id="ea791-119">单击**应用**接受所做的更改，然后才能继续进行配置，或单击**确定**验证所做的更改，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="ea791-119">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea791-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ea791-120">See Also</span></span>  
 [<span data-ttu-id="ea791-121">配置 AS2 协议属性</span><span class="sxs-lookup"><span data-stu-id="ea791-121">Configuring AS2 Agreement Properties</span></span>](../core/configuring-as2-agreement-properties.md)