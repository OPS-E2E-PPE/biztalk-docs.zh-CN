---
title: 配置 Mdn 的 HTTP 设置 |Microsoft Docs
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
ms.openlocfilehash: 40496efd556d30f87f33d647ab97edb123453c5f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65355421"
---
# <a name="configuring-http-settings-for-mdns"></a><span data-ttu-id="63d40-102">配置 Mdn 的 HTTP 设置</span><span class="sxs-lookup"><span data-stu-id="63d40-102">Configuring HTTP Settings for MDNs</span></span>
<span data-ttu-id="63d40-103">作为 MDN 相关 HTTP 设置的一部分，可以指定用来接收 Mdn 的 Web 服务器所需的属性。</span><span class="sxs-lookup"><span data-stu-id="63d40-103">As part of MDN-related HTTP settings, you can specify the properties expected by the Web server that receives the MDNs.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="63d40-104">如果你清除了所有属性会都禁用此页上**本地 BizTalk 处理参与方或支持来自此参与方发送消息的接收的消息**要为其创建的参与方时的复选框协议。</span><span class="sxs-lookup"><span data-stu-id="63d40-104">All the properties are disabled on this page if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
>   
>  <span data-ttu-id="63d40-105">仅在与参与方所发送交换的属性相对应的单向协议选项卡上禁用这些属性。</span><span class="sxs-lookup"><span data-stu-id="63d40-105">The properties are disabled only on the one-way agreement tab that corresponds to the properties for interchanges being sent from the party.</span></span> <span data-ttu-id="63d40-106">例如，如果创建两个参与方 Party A 和参与方 B，并且对于参与方 A 清除该复选框，上述列表中的属性上禁用**参与方 A-> 参与方 B**单向协议选项卡。</span><span class="sxs-lookup"><span data-stu-id="63d40-106">For example, if you create two parties Party A and Party B and for Party A, you cleared the check box, the above list of properties are disabled on the **Party A->Party B** one-way agreement tab.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="63d40-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="63d40-107">Prerequisites</span></span>  
 <span data-ttu-id="63d40-108">必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。</span><span class="sxs-lookup"><span data-stu-id="63d40-108">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-mdn-related-http-settings"></a><span data-ttu-id="63d40-109">若要配置与 MDN 相关 HTTP 设置</span><span class="sxs-lookup"><span data-stu-id="63d40-109">To configure MDN-related HTTP settings</span></span>  
  
1.  <span data-ttu-id="63d40-110">创建 AS2 协议中所述[配置常规设置 (AS2)](../core/configuring-general-settings-as2.md)。</span><span class="sxs-lookup"><span data-stu-id="63d40-110">Create an AS2 agreement as described in [Configuring General Settings (AS2)](../core/configuring-general-settings-as2.md).</span></span> <span data-ttu-id="63d40-111">若要更新现有 AS2 协议，请右键单击中的协议**参与方和业务配置文件**页，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="63d40-111">To update an existing AS2 agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="63d40-112">在单向协议选项卡下**本地主机设置**部分中，单击**Mdn 的 HTTP 设置**。</span><span class="sxs-lookup"><span data-stu-id="63d40-112">On a one-way agreement tab, under **Local Host Settings** section, click **HTTP Settings for MDNs**.</span></span>  
  
3.  <span data-ttu-id="63d40-113">选择**忽略 SSL 证书名称不匹配**接受复选框以确保如果服务器名称与为其生成 SSL 证书的服务器名称不匹配，将仍 SSL 连接。</span><span class="sxs-lookup"><span data-stu-id="63d40-113">Select the **Ignore SSL Certificate Name mismatch** check box to ensure that if the server name does not match the server name that the SSL certificate was generated for, the SSL connection would still be accepted.</span></span>  
  
4.  <span data-ttu-id="63d40-114">单击**HTTP 预期 100 继续**将 HTTP Expect 标头设置为 100-continue，这将指定不在初始 HTTP 请求中，但等待服务器请求内容包含已发布的数据。</span><span class="sxs-lookup"><span data-stu-id="63d40-114">Click **HTTP expect 100 continue** to set the HTTP Expect header to 100-continue, which specifies that the posted data not be included in the initial HTTP request, but waits for the server to request the content.</span></span>  
  
5.  <span data-ttu-id="63d40-115">单击**保持 HTTP 连接保持活动状态**请求的 HTTP 连接保持活动状态后请求和响应周期已结束。</span><span class="sxs-lookup"><span data-stu-id="63d40-115">Click **Keep HTTP connection alive** to request that an HTTP connection be kept alive after a request and response cycle has been completed.</span></span>  
  
6.  <span data-ttu-id="63d40-116">单击**展开 HTTP 标头**以将 HTTP 内容类型标头展开为单个行。</span><span class="sxs-lookup"><span data-stu-id="63d40-116">Click **Unfold HTTP headers** to unfold the HTTP content-type header into a single line.</span></span>  
  
7.  <span data-ttu-id="63d40-117">单击**Apply**以接受更改，然后才能继续进行配置，或单击**确定**以验证所做的更改，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="63d40-117">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63d40-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="63d40-118">See Also</span></span>  
 [<span data-ttu-id="63d40-119">配置本地主机设置 (AS2)</span><span class="sxs-lookup"><span data-stu-id="63d40-119">Configuring Local Host Settings (AS2)</span></span>](../core/configuring-local-host-settings-as2.md)