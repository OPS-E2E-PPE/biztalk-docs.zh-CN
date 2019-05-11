---
title: 配置签名证书 (AS2) |Microsoft Docs
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
ms.openlocfilehash: aa26611b0937385b74773aa4cd9c78477c7e3378
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65355200"
---
# <a name="configuring-signature-certificates-as2"></a><span data-ttu-id="a89fb-102">配置签名证书 (AS2)</span><span class="sxs-lookup"><span data-stu-id="a89fb-102">Configuring Signature Certificates (AS2)</span></span>
<span data-ttu-id="a89fb-103">作为此页上设置的一部分，可以指定要用于签名的所有传出消息和 MDN 的解析此协议的证书。</span><span class="sxs-lookup"><span data-stu-id="a89fb-103">As part of the settings on this page, you can specify the certificates to be used for signing all outgoing messages and MDN that resolve to this agreement.</span></span> <span data-ttu-id="a89fb-104">此页上的设置替代的 BizTalk 组属性一部分提供的证书设置。</span><span class="sxs-lookup"><span data-stu-id="a89fb-104">The settings on this page override the certificate settings provided as part of the BizTalk Group properties.</span></span> <span data-ttu-id="a89fb-105">有关如何使用证书的详细信息，请参阅[as2 配置证书](../core/configuring-certificates-for-as2.md)。</span><span class="sxs-lookup"><span data-stu-id="a89fb-105">For more information on how certificates are used, see [Configuring Certificates for AS2](../core/configuring-certificates-for-as2.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a89fb-106">没有属性禁用此页上，即使您清除**本地 BizTalk 处理参与方或支持来自此参与方发送消息的接收的消息**要为其创建的参与方时的复选框协议。</span><span class="sxs-lookup"><span data-stu-id="a89fb-106">No properties are disabled on this page even if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a89fb-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="a89fb-107">Prerequisites</span></span>  
 <span data-ttu-id="a89fb-108">必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。</span><span class="sxs-lookup"><span data-stu-id="a89fb-108">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-agreement-level-signature-certificate"></a><span data-ttu-id="a89fb-109">若要配置协议层签名证书</span><span class="sxs-lookup"><span data-stu-id="a89fb-109">To configure agreement-level signature certificate</span></span>  
  
1.  <span data-ttu-id="a89fb-110">创建 AS2 协议中所述[配置常规设置 (AS2)](../core/configuring-general-settings-as2.md)。</span><span class="sxs-lookup"><span data-stu-id="a89fb-110">Create an AS2 agreement as described in [Configuring General Settings (AS2)](../core/configuring-general-settings-as2.md).</span></span> <span data-ttu-id="a89fb-111">若要更新现有 AS2 协议，请右键单击中的协议**参与方和业务配置文件**页，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="a89fb-111">To update an existing AS2 agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="a89fb-112">在单向协议选项卡上，单击**签名证书**。</span><span class="sxs-lookup"><span data-stu-id="a89fb-112">On a one-way agreement tab, click **Signature Certificates**.</span></span>  
  
3.  <span data-ttu-id="a89fb-113">选择**覆盖组签名证书**复选框以使用此页中提供的签名传出 AS2 消息和 MDN 的证书。</span><span class="sxs-lookup"><span data-stu-id="a89fb-113">Select the **Override group signing certificate** check box to use the certificate provided in this page for signing outgoing AS2 messages and MDN.</span></span>  
  
4.  <span data-ttu-id="a89fb-114">单击**浏览**以显示**选择证书**对话框中，在其中选择要应用到由此参与方传输的消息的签名证书。</span><span class="sxs-lookup"><span data-stu-id="a89fb-114">Click **Browse** to display the **Select Certificate** dialog box, where you select the signature certificate to apply to messages transmitted by this party.</span></span>  
  
5.  <span data-ttu-id="a89fb-115">**公用名**文本框显示所选证书的说明。</span><span class="sxs-lookup"><span data-stu-id="a89fb-115">The **Common Name** text box displays a description of the selected certificate.</span></span>  
  
6.  <span data-ttu-id="a89fb-116">**指纹**文本框将显示证书的指纹。</span><span class="sxs-lookup"><span data-stu-id="a89fb-116">The **Thumbprint** text box displays the thumbprint of certificate.</span></span> <span data-ttu-id="a89fb-117">证书指纹的格式 HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH，其中 H 为十六进制数字 （从 0 到 9 的数字） 或为从 A 到 F 的字母。</span><span class="sxs-lookup"><span data-stu-id="a89fb-117">The certificate thumbprint has the format HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH, where H is a hexadecimal digit (a number from 0 through 9 or a letter from A through F).</span></span>  
  
7.  <span data-ttu-id="a89fb-118">单击**删除证书**若要删除所选的证书。</span><span class="sxs-lookup"><span data-stu-id="a89fb-118">Click **Remove Certificate** to remove the selected certificate.</span></span>  
  
8.  <span data-ttu-id="a89fb-119">单击**Apply**以接受更改，然后才能继续进行配置，或单击**确定**以验证所做的更改，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="a89fb-119">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a89fb-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="a89fb-120">See Also</span></span>  
 [<span data-ttu-id="a89fb-121">配置 AS2 协议属性</span><span class="sxs-lookup"><span data-stu-id="a89fb-121">Configuring AS2 Agreement Properties</span></span>](../core/configuring-as2-agreement-properties.md)