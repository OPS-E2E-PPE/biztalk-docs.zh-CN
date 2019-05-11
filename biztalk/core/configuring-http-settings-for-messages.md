---
title: 配置消息的 HTTP 设置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3ed400f1-561d-4812-adf1-20e4300fd048
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3a5e216ec76fa4ccbf6255d802f337c9c0ac47ca
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391049"
---
# <a name="configuring-http-settings-for-messages"></a><span data-ttu-id="f6ce2-102">配置消息的 HTTP 设置</span><span class="sxs-lookup"><span data-stu-id="f6ce2-102">Configuring HTTP Settings for Messages</span></span>
<span data-ttu-id="f6ce2-103">作为与消息相关的 HTTP 设置的一部分，可以指定接收 AS2 消息的 Web 服务器所需的属性。</span><span class="sxs-lookup"><span data-stu-id="f6ce2-103">As part of message-related HTTP settings, you can specify the properties expected by the Web server that receives AS2 messages.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f6ce2-104">没有属性上将禁用**参与方 A-> 参与方 B**单向协议选项卡，如果您清除**本地 BizTalk 处理参与方或支持来自此参与方发送消息的接收的消息**复选框为参与方 a。但是，禁用中相同页面上的所有属性**参与方 B-> 参与方 A**选项卡上，如果您创建参与方 A.时选中复选框</span><span class="sxs-lookup"><span data-stu-id="f6ce2-104">No properties are disabled on **Party A->Party B** one-way agreement tab if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box for Party A. However, all the properties are disabled on the same page in the **Party B->Party A** tab if you selected the check box while creating Party A.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f6ce2-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="f6ce2-105">Prerequisites</span></span>  
 <span data-ttu-id="f6ce2-106">必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。</span><span class="sxs-lookup"><span data-stu-id="f6ce2-106">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-message-related-http-settings"></a><span data-ttu-id="f6ce2-107">若要配置与消息相关的 HTTP 设置</span><span class="sxs-lookup"><span data-stu-id="f6ce2-107">To configure message-related HTTP settings</span></span>  
  
1.  <span data-ttu-id="f6ce2-108">创建 AS2 协议中所述[配置常规设置 (AS2)](../core/configuring-general-settings-as2.md)。</span><span class="sxs-lookup"><span data-stu-id="f6ce2-108">Create an AS2 agreement as described in [Configuring General Settings (AS2)](../core/configuring-general-settings-as2.md).</span></span> <span data-ttu-id="f6ce2-109">若要更新现有 AS2 协议，请右键单击中的协议**参与方和业务配置文件**页，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="f6ce2-109">To update an existing AS2 agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="f6ce2-110">在单向协议选项卡下**本地主机设置**部分中，单击**消息的 HTTP 设置**。</span><span class="sxs-lookup"><span data-stu-id="f6ce2-110">On a one-way agreement tab, under **Local Host Settings** section, click **HTTP Settings for Messages**.</span></span>  
  
3.  <span data-ttu-id="f6ce2-111">选择**忽略 SSL 证书名称不匹配**接受复选框以确保如果服务器名称与为其生成 SSL 证书的服务器名称不匹配，将仍 SSL 连接。</span><span class="sxs-lookup"><span data-stu-id="f6ce2-111">Select the **Ignore SSL Certificate Name mismatch** check box to ensure that if the server name does not match the server name that the SSL certificate was generated for, the SSL connection would still be accepted.</span></span>  
  
4.  <span data-ttu-id="f6ce2-112">单击**HTTP 预期 100 继续**将 HTTP Expect 标头设置为 100-continue，这将指定不在初始 HTTP 请求中，但等待服务器请求内容包含已发布的数据。</span><span class="sxs-lookup"><span data-stu-id="f6ce2-112">Click **HTTP expect 100 continue** to set the HTTP Expect header to 100-continue, which specifies that the posted data not be included in the initial HTTP request, but waits for the server to request the content.</span></span>  
  
5.  <span data-ttu-id="f6ce2-113">单击**保持 HTTP 连接保持活动状态**请求的 HTTP 连接保持活动状态后请求和响应周期已结束。</span><span class="sxs-lookup"><span data-stu-id="f6ce2-113">Click **Keep HTTP connection alive** to request that an HTTP connection be kept alive after a request and response cycle has been completed.</span></span>  
  
6.  <span data-ttu-id="f6ce2-114">单击**展开 HTTP 标头**以将 HTTP 内容类型标头展开为单个行。</span><span class="sxs-lookup"><span data-stu-id="f6ce2-114">Click **Unfold HTTP headers** to unfold the HTTP content-type header into a single line.</span></span>  
  
7.  <span data-ttu-id="f6ce2-115">单击**Apply**以接受更改，然后才能继续进行配置，或单击**确定**以验证所做的更改，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="f6ce2-115">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6ce2-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="f6ce2-116">See Also</span></span>  
 [<span data-ttu-id="f6ce2-117">配置本地主机设置 (AS2)</span><span class="sxs-lookup"><span data-stu-id="f6ce2-117">Configuring Local Host Settings (AS2)</span></span>](../core/configuring-local-host-settings-as2.md)