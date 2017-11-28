---
title: "配置收件人 MDN 设置 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eae6431d-a2b9-4889-a29c-720e801a644e
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dafe17a0ad357b840b31d8a10c67e1ae3cc1e415
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-receiver-mdn-settings"></a><span data-ttu-id="aeac9-102">配置收件人 MDN 设置</span><span class="sxs-lookup"><span data-stu-id="aeac9-102">Configuring Receiver MDN Settings</span></span>
<span data-ttu-id="aeac9-103">作为接收器 MDN 设置的一部分，您可以根据 AS2 消息标头来指定控制 MDN 生成的属性。</span><span class="sxs-lookup"><span data-stu-id="aeac9-103">As part of receiver MDN settings, you can specify the properties that govern MDN generation based on the AS2 message header.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="aeac9-104">没有属性上将禁用**A 方-> 方 B**单向协议选项卡，如果你清除**本地 BizTalk 处理接收方或支持从该参与方发送消息的消息**复选框当事方 a。但是，将所有属性都禁用中相同页面上**B 方-> A 方**选项卡上，如果创建 a 方。 时选中复选框</span><span class="sxs-lookup"><span data-stu-id="aeac9-104">No properties are disabled on **Party A->Party B** one-way agreement tab if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box for Party A. However, all the properties are disabled on the same page in the **Party B->Party A** tab if you selected the check box while creating Party A.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="aeac9-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="aeac9-105">Prerequisites</span></span>  
 <span data-ttu-id="aeac9-106">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="aeac9-106">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-receiver-mdn-settings"></a><span data-ttu-id="aeac9-107">配置接收方 MDN 设置</span><span class="sxs-lookup"><span data-stu-id="aeac9-107">To configure receiver MDN settings</span></span>  
  
1.  <span data-ttu-id="aeac9-108">创建 AS2 协议中所述[配置常规设置 (AS2)](../core/configuring-general-settings-as2.md)。</span><span class="sxs-lookup"><span data-stu-id="aeac9-108">Create an AS2 agreement as described in [Configuring General Settings (AS2)](../core/configuring-general-settings-as2.md).</span></span> <span data-ttu-id="aeac9-109">若要更新现有 AS2 协议，右键单击在协议**方和业务配置文件**页，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="aeac9-109">To update an existing AS2 agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="aeac9-110">单向协议选项卡上，在**本地主机设置**部分中，单击**收件人 MDN 设置**。</span><span class="sxs-lookup"><span data-stu-id="aeac9-110">On a one-way agreement tab, under **Local Host Settings** section, click **Receiver MDN Settings**.</span></span>  
  
3.  <span data-ttu-id="aeac9-111">如果你没有检查**使用验证和 MDN 的协议设置，而不是消息标头**中的属性**验证**页上，你可以选择具有发送 MDN，方签名的 MDN，如果MDN 生成通过**处置-到通知**AS2 标头，但**处置通知选项**标头不会启用签名。</span><span class="sxs-lookup"><span data-stu-id="aeac9-111">If you did not check the **Use agreement settings for validation and MDN instead of message header** property in the **Validations** page, you can choose to have the party sending the MDN, sign the MDN if generation of the MDN is enabled by the **Disposition-Notification-to** AS2 header, but the **Disposition-Notification-Options** header does not enable signing.</span></span> <span data-ttu-id="aeac9-112">发生这种情况**处置通知选项**未设置，或设置为可选。</span><span class="sxs-lookup"><span data-stu-id="aeac9-112">This can occur if **Disposition-Notification-Options** is either not set or is set to optional.</span></span> <span data-ttu-id="aeac9-113">你可以通过单击来实现**登录请求 MDN 不预设处置通知选项标头是否已签名回执协议标头设置为可选**。</span><span class="sxs-lookup"><span data-stu-id="aeac9-113">You can do so by clicking **Sign requested MDN if Disposition-Notification-Option header is not preset or if Signed-Receipt-Protocol header is set to optional**.</span></span>  
  
4.  <span data-ttu-id="aeac9-114">你可以输入中的文本**MDN 文本**字段可以在参与方发送 MDN 将其添加到 MDN 消息 （在内容说明字段中）。</span><span class="sxs-lookup"><span data-stu-id="aeac9-114">You can enter a text in the **MDN Text** field to have the party sending the MDN add it to the MDN message (under the Content-Description field).</span></span> <span data-ttu-id="aeac9-115">此设置十分适用，并且不用考虑是否根据 AS2 标头或协议属性生成 MDN。</span><span class="sxs-lookup"><span data-stu-id="aeac9-115">This setting is applicable irrespective of whether the MDN was generated based upon the AS2 headers or the agreement properties.</span></span>  
  
5.  <span data-ttu-id="aeac9-116">单击**应用**接受所做的更改，然后才能继续进行配置，或单击**确定**验证所做的更改，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="aeac9-116">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aeac9-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="aeac9-117">See Also</span></span>  
 [<span data-ttu-id="aeac9-118">配置本地主机设置 (AS2)</span><span class="sxs-lookup"><span data-stu-id="aeac9-118">Configuring Local Host Settings (AS2)</span></span>](../core/configuring-local-host-settings-as2.md)