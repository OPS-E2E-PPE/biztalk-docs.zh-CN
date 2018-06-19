---
title: 配置回退本地主机设置 （EDIFACT 事务集设置） |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0142b3fc-009f-4da5-b34d-dddf4fb96e0f
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 931db62edda264a6fff0ddb422bd41b243cd29ae
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232957"
---
# <a name="configuring-fallback-local-host-settings-edifact-transaction-set-settings"></a><span data-ttu-id="70f66-102">配置回退本地主机设置（EDIFACT-事务集设置）</span><span class="sxs-lookup"><span data-stu-id="70f66-102">Configuring Fallback Local Host Settings (EDIFACT-Transaction Set Settings)</span></span>
<span data-ttu-id="70f66-103">为了处理传入的交换，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 必须确定在处理和验证交换时需要使用的架构。</span><span class="sxs-lookup"><span data-stu-id="70f66-103">To process an incoming interchange, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] must determine the schema that it needs to use in processing and validating the interchange.</span></span> <span data-ttu-id="70f66-104">这包括确定与架构关联的目标命名空间和确定要使用的架构。</span><span class="sxs-lookup"><span data-stu-id="70f66-104">This consists of determining the target namespace associated with the schema, and determining the schema to be used.</span></span> <span data-ttu-id="70f66-105">在后备协议的此页中，可输入要在确定目标命名空间时使用的属性。</span><span class="sxs-lookup"><span data-stu-id="70f66-105">In this page of fallback agreement, you enter the properties to be used in determining the target namespace.</span></span> <span data-ttu-id="70f66-106">中所述 BizTalk Server 如何确定架构[协议解析、 架构发现和接收 EDI 消息的授权](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md)。</span><span class="sxs-lookup"><span data-stu-id="70f66-106">How BizTalk Server determines the schema is described in [Agreement Resolution, Schema Discovery, and Authorization for Received EDI Messages](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="70f66-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="70f66-107">Prerequisites</span></span>  
 <span data-ttu-id="70f66-108">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="70f66-108">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-local-host-settings-for-transaction-sets"></a><span data-ttu-id="70f66-109">要配置事务集的本地主机设置，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="70f66-109">To configure local host settings for transaction sets</span></span>  
  
1.  <span data-ttu-id="70f66-110">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**方**节点，，然后单击**EDIFACT 回退设置**。</span><span class="sxs-lookup"><span data-stu-id="70f66-110">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Parties** node, and then click **EDIFACT Fallback Settings**.</span></span>  
  
2.  <span data-ttu-id="70f66-111">在**EDIFACT 回退设置**对话框中，在**EDIFACT 协议页**选项卡上，在**事务设置设置**部分中，单击**本地主机设置**。</span><span class="sxs-lookup"><span data-stu-id="70f66-111">In the **EDIFACT Fallback Settings** dialog box, in the **EDIFACT Agreement Pages** tab, under the **Transaction Set Settings** section, click **Local Host Settings**.</span></span>  
  
3.  <span data-ttu-id="70f66-112">选择**创建为尾随分隔符的空 XML 标记**能够包含的尾随分隔符的空 XML 标记交换发件人。</span><span class="sxs-lookup"><span data-stu-id="70f66-112">Select **Create empty XML tags for trailing separators** to have the interchange sender include empty XML tags for trailing separators.</span></span>  
  
4.  <span data-ttu-id="70f66-113">选择**使用点 （.） 作为小数分隔符**若要启用 BizTalk Server 包括句点 （.） 中包含的小数的交换创建的 XML 消息。</span><span class="sxs-lookup"><span data-stu-id="70f66-113">Select **Use Dot (.) as decimal separator** to enable BizTalk Server include a dot (.) in the XML message created out of an interchange that contains a decimal number.</span></span>  
  
5.  <span data-ttu-id="70f66-114">有关**目标 Namespace**、 输入 （或从下拉列表中选择） 的目标命名空间，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将使用来确定要处理收到的消息的架构</span><span class="sxs-lookup"><span data-stu-id="70f66-114">For **Target Namespace**, enter (or select from the drop-down list) the target namespace that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will use to determine the schema to process the received message with</span></span>  
  
6.  <span data-ttu-id="70f66-115">单击**应用**接受所做的更改，然后才能继续进行配置，或单击**确定**验证所做的更改，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="70f66-115">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70f66-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="70f66-116">See Also</span></span>  
 [<span data-ttu-id="70f66-117">为事务配置 EDIFACT 回退协议属性设置</span><span class="sxs-lookup"><span data-stu-id="70f66-117">Configuring EDIFACT Fallback Agreement Properties for Transaction Set Settings</span></span>](../core/configuring-edifact-fallback-agreement-properties-for-transaction-set-settings.md)