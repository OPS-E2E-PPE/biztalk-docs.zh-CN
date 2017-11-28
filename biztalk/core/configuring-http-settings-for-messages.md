---
title: "配置消息的 HTTP 设置 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3ed400f1-561d-4812-adf1-20e4300fd048
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d15ebb5ff5be6678c4dc2aee3f9333f36c75c89f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-http-settings-for-messages"></a><span data-ttu-id="2b40d-102">配置消息的 HTTP 设置</span><span class="sxs-lookup"><span data-stu-id="2b40d-102">Configuring HTTP Settings for Messages</span></span>
<span data-ttu-id="2b40d-103">作为与消息相关的 HTTP 设置的一部分，您可以指定接收 AS2 消息的 Web 服务器所要求的属性。</span><span class="sxs-lookup"><span data-stu-id="2b40d-103">As part of message-related HTTP settings, you can specify the properties expected by the Web server that receives AS2 messages.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2b40d-104">没有属性上将禁用**A 方-> 方 B**单向协议选项卡，如果你清除**本地 BizTalk 处理接收方或支持从该参与方发送消息的消息**复选框当事方 a。但是，将所有属性都禁用中相同页面上**B 方-> A 方**选项卡上，如果创建 a 方。 时选中复选框</span><span class="sxs-lookup"><span data-stu-id="2b40d-104">No properties are disabled on **Party A->Party B** one-way agreement tab if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box for Party A. However, all the properties are disabled on the same page in the **Party B->Party A** tab if you selected the check box while creating Party A.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="2b40d-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="2b40d-105">Prerequisites</span></span>  
 <span data-ttu-id="2b40d-106">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="2b40d-106">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-message-related-http-settings"></a><span data-ttu-id="2b40d-107">配置与消息相关的 HTTP 设置</span><span class="sxs-lookup"><span data-stu-id="2b40d-107">To configure message-related HTTP settings</span></span>  
  
1.  <span data-ttu-id="2b40d-108">创建 AS2 协议中所述[配置常规设置 (AS2)](../core/configuring-general-settings-as2.md)。</span><span class="sxs-lookup"><span data-stu-id="2b40d-108">Create an AS2 agreement as described in [Configuring General Settings (AS2)](../core/configuring-general-settings-as2.md).</span></span> <span data-ttu-id="2b40d-109">若要更新现有 AS2 协议，右键单击在协议**方和业务配置文件**页，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="2b40d-109">To update an existing AS2 agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="2b40d-110">单向协议选项卡上，在**本地主机设置**部分中，单击**消息的 HTTP 设置**。</span><span class="sxs-lookup"><span data-stu-id="2b40d-110">On a one-way agreement tab, under **Local Host Settings** section, click **HTTP Settings for Messages**.</span></span>  
  
3.  <span data-ttu-id="2b40d-111">选择**忽略 SSL 证书名称不匹配**接受复选框以确保如果服务器名称与生成的 SSL 证书所针对的服务器名称不匹配，将仍 SSL 连接。</span><span class="sxs-lookup"><span data-stu-id="2b40d-111">Select the **Ignore SSL Certificate Name mismatch** check box to ensure that if the server name does not match the server name that the SSL certificate was generated for, the SSL connection would still be accepted.</span></span>  
  
4.  <span data-ttu-id="2b40d-112">单击**HTTP 预期 100 继续**将预期 HTTP 标头设置为 100-继续，请指定不在初始 HTTP 请求，但等待服务器请求内容包括已发布的数据。</span><span class="sxs-lookup"><span data-stu-id="2b40d-112">Click **HTTP expect 100 continue** to set the HTTP Expect header to 100-continue, which specifies that the posted data not be included in the initial HTTP request, but waits for the server to request the content.</span></span>  
  
5.  <span data-ttu-id="2b40d-113">单击**保持 HTTP 连接处于活动状态**请求，请求和响应周期完成后，HTTP 连接将保持活动状态。</span><span class="sxs-lookup"><span data-stu-id="2b40d-113">Click **Keep HTTP connection alive** to request that an HTTP connection be kept alive after a request and response cycle has been completed.</span></span>  
  
6.  <span data-ttu-id="2b40d-114">单击**展开 HTTP 标头**展开到一行的 HTTP 内容类型标头。</span><span class="sxs-lookup"><span data-stu-id="2b40d-114">Click **Unfold HTTP headers** to unfold the HTTP content-type header into a single line.</span></span>  
  
7.  <span data-ttu-id="2b40d-115">单击**应用**接受所做的更改，然后才能继续进行配置，或单击**确定**验证所做的更改，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="2b40d-115">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b40d-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2b40d-116">See Also</span></span>  
 [<span data-ttu-id="2b40d-117">配置本地主机设置 (AS2)</span><span class="sxs-lookup"><span data-stu-id="2b40d-117">Configuring Local Host Settings (AS2)</span></span>](../core/configuring-local-host-settings-as2.md)