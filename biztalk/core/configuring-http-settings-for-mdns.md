---
title: 配置 Mdn 的 HTTP 设置 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5c877e85-7887-43a9-9fd4-0853b573213f
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f74ba2eaf11e8beed3e28d10beb9f95b2f0f6194
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233333"
---
# <a name="configuring-http-settings-for-mdns"></a><span data-ttu-id="96764-102">配置 MDN 的 HTTP 设置</span><span class="sxs-lookup"><span data-stu-id="96764-102">Configuring HTTP Settings for MDNs</span></span>
<span data-ttu-id="96764-103">作为 MDN 相关 HTTP 设置的一部分，您可以指定接收 MDN 的 Web 服务器所需的属性。</span><span class="sxs-lookup"><span data-stu-id="96764-103">As part of MDN-related HTTP settings, you can specify the properties expected by the Web server that receives the MDNs.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="96764-104">如果你清除了所有属性会被都禁用此页上**本地 BizTalk 处理接收方或支持从该参与方发送消息的消息**时正在创建你为其创建参与方的复选框协议。</span><span class="sxs-lookup"><span data-stu-id="96764-104">All the properties are disabled on this page if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
>   
>  <span data-ttu-id="96764-105">仅在与从参与方发送交换的属性相对应的单向协议选项卡上禁用这些属性。</span><span class="sxs-lookup"><span data-stu-id="96764-105">The properties are disabled only on the one-way agreement tab that corresponds to the properties for interchanges being sent from the party.</span></span> <span data-ttu-id="96764-106">例如，如果创建两个参与方 A 方和方 B 和 A 的当事方，清除复选框，则上面的属性列表会禁用上**A 方-> 方 B**单向协议选项卡。</span><span class="sxs-lookup"><span data-stu-id="96764-106">For example, if you create two parties Party A and Party B and for Party A, you cleared the check box, the above list of properties are disabled on the **Party A->Party B** one-way agreement tab.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="96764-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="96764-107">Prerequisites</span></span>  
 <span data-ttu-id="96764-108">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="96764-108">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-mdn-related-http-settings"></a><span data-ttu-id="96764-109">若要配置的相关 MDN 的 HTTP 设置</span><span class="sxs-lookup"><span data-stu-id="96764-109">To configure MDN-related HTTP settings</span></span>  
  
1.  <span data-ttu-id="96764-110">创建 AS2 协议中所述[配置常规设置 (AS2)](../core/configuring-general-settings-as2.md)。</span><span class="sxs-lookup"><span data-stu-id="96764-110">Create an AS2 agreement as described in [Configuring General Settings (AS2)](../core/configuring-general-settings-as2.md).</span></span> <span data-ttu-id="96764-111">若要更新现有 AS2 协议，右键单击在协议**方和业务配置文件**页，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="96764-111">To update an existing AS2 agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="96764-112">单向协议选项卡上，在**本地主机设置**部分中，单击**Mdn 的 HTTP 设置**。</span><span class="sxs-lookup"><span data-stu-id="96764-112">On a one-way agreement tab, under **Local Host Settings** section, click **HTTP Settings for MDNs**.</span></span>  
  
3.  <span data-ttu-id="96764-113">选择**忽略 SSL 证书名称不匹配**接受复选框以确保如果服务器名称与生成的 SSL 证书所针对的服务器名称不匹配，将仍 SSL 连接。</span><span class="sxs-lookup"><span data-stu-id="96764-113">Select the **Ignore SSL Certificate Name mismatch** check box to ensure that if the server name does not match the server name that the SSL certificate was generated for, the SSL connection would still be accepted.</span></span>  
  
4.  <span data-ttu-id="96764-114">单击**HTTP 预期 100 继续**将预期 HTTP 标头设置为 100-继续，请指定不在初始 HTTP 请求，但等待服务器请求内容包括已发布的数据。</span><span class="sxs-lookup"><span data-stu-id="96764-114">Click **HTTP expect 100 continue** to set the HTTP Expect header to 100-continue, which specifies that the posted data not be included in the initial HTTP request, but waits for the server to request the content.</span></span>  
  
5.  <span data-ttu-id="96764-115">单击**保持 HTTP 连接处于活动状态**请求，请求和响应周期完成后，HTTP 连接将保持活动状态。</span><span class="sxs-lookup"><span data-stu-id="96764-115">Click **Keep HTTP connection alive** to request that an HTTP connection be kept alive after a request and response cycle has been completed.</span></span>  
  
6.  <span data-ttu-id="96764-116">单击**展开 HTTP 标头**展开到一行的 HTTP 内容类型标头。</span><span class="sxs-lookup"><span data-stu-id="96764-116">Click **Unfold HTTP headers** to unfold the HTTP content-type header into a single line.</span></span>  
  
7.  <span data-ttu-id="96764-117">单击**应用**接受所做的更改，然后才能继续进行配置，或单击**确定**验证所做的更改，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="96764-117">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96764-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="96764-118">See Also</span></span>  
 [<span data-ttu-id="96764-119">配置本地主机设置 (AS2)</span><span class="sxs-lookup"><span data-stu-id="96764-119">Configuring Local Host Settings (AS2)</span></span>](../core/configuring-local-host-settings-as2.md)