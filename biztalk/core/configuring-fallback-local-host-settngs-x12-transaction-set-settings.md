---
title: 配置回退本地主机设置 （X12-事务集设置） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 68511199-a7ed-45b3-807d-70378b2c6ebb
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3eb3ed007a30e2d65c4d65aebe98ebabf2f93c6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391213"
---
# <a name="configuring-fallback-local-host-settngs-x12-transaction-set-settings"></a><span data-ttu-id="85cc3-102">配置回退本地主机设置（X12-事务集设置）</span><span class="sxs-lookup"><span data-stu-id="85cc3-102">Configuring Fallback Local Host Settngs (X12-Transaction Set Settings)</span></span>
<span data-ttu-id="85cc3-103">若要处理传入的交换，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]必须确定它需要使用在处理和验证交换的架构。</span><span class="sxs-lookup"><span data-stu-id="85cc3-103">To process an incoming interchange, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] must determine the schema that it needs to use in processing and validating the interchange.</span></span> <span data-ttu-id="85cc3-104">这包括确定与架构相关联的目标命名空间并确定要使用的架构。</span><span class="sxs-lookup"><span data-stu-id="85cc3-104">This consists of determining the target namespace associated with the schema, and determining the schema to be used.</span></span> <span data-ttu-id="85cc3-105">在备用协议的此页上，指定备用目标命名空间。</span><span class="sxs-lookup"><span data-stu-id="85cc3-105">In this page of the fallback agreement, you specify the fallback target namespace.</span></span> <span data-ttu-id="85cc3-106">如何[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]确定架构中，请参阅[协议解析、 架构发现和收到的 EDI 消息的授权](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md)。</span><span class="sxs-lookup"><span data-stu-id="85cc3-106">How [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] determines the schema is described in [Agreement Resolution, Schema Discovery, and Authorization for Received EDI Messages](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="85cc3-107">本主题还适用于与 HIPAA 相关的设置。</span><span class="sxs-lookup"><span data-stu-id="85cc3-107">This topic applies also to HIPAA-related settings.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="85cc3-108">先决条件</span><span class="sxs-lookup"><span data-stu-id="85cc3-108">Prerequisites</span></span>  
 <span data-ttu-id="85cc3-109">必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。</span><span class="sxs-lookup"><span data-stu-id="85cc3-109">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-local-host-settings-for-transaction-sets"></a><span data-ttu-id="85cc3-110">若要配置本地主机设置为事务集</span><span class="sxs-lookup"><span data-stu-id="85cc3-110">To configure local host settings for transaction sets</span></span>  
  
1. <span data-ttu-id="85cc3-111">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**方**节点，，然后单击**X12 后备设置**。</span><span class="sxs-lookup"><span data-stu-id="85cc3-111">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Parties** node, and then click **X12 Fallback Settings**.</span></span>  
  
2. <span data-ttu-id="85cc3-112">在中**X12 后备设置**对话框中**X12 协议页**选项卡上，在**事务集设置**部分中，单击**本地主机设置**.</span><span class="sxs-lookup"><span data-stu-id="85cc3-112">In the **X12 Fallback Settings** dialog box, in the **X12 Agreement Pages** tab, under the **Transaction Set Settings** section, click **Local Host Settings**.</span></span>  
  
3. <span data-ttu-id="85cc3-113">选择**将隐式小数格式 Nn 十进制数值**若要使用的中间 XML 中 BizTalk Server 的十进制数字值格式 Nn 指定的 EDI 数值转换。</span><span class="sxs-lookup"><span data-stu-id="85cc3-113">Select **Convert implied decimal format Nn to base 10 numeric value** to convert an EDI number that is specified with the format Nn into a base-10 numeric value in the intermediate XML in BizTalk Server.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="85cc3-114">在此转换后的中间 XML 可能无法通过长度验证。</span><span class="sxs-lookup"><span data-stu-id="85cc3-114">After this conversion, the intermediate XML may fail length validation.</span></span> <span data-ttu-id="85cc3-115">这是因为采用以 10 为基数的数字格式的数字包含小数点，使其长度超过一个以 Nn 格式。</span><span class="sxs-lookup"><span data-stu-id="85cc3-115">This occurs because the number in the base-10 numeric format includes a decimal, making its length one greater than the number in Nn format.</span></span> <span data-ttu-id="85cc3-116">可以通过添加的值来解决此问题**1**为最小/最大长度值。</span><span class="sxs-lookup"><span data-stu-id="85cc3-116">You can resolve this issue by adding a value of **1** to the minimum/maximum length value.</span></span>  
  
4. <span data-ttu-id="85cc3-117">选择**创建为尾部分隔符的空 XML 标记**以使交换发送方包含为尾部分隔符的空 XML 标记。</span><span class="sxs-lookup"><span data-stu-id="85cc3-117">Select **Create empty XML tags for trailing separators** to have the interchange sender include empty XML tags for trailing separators.</span></span>  
  
5. <span data-ttu-id="85cc3-118">有关**目标 Namespace**，输入 （或从下拉列表中选择） 的目标命名空间的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用来确定处理接收的消息的架构。</span><span class="sxs-lookup"><span data-stu-id="85cc3-118">For **Target Namespace**, enter (or select from the drop-down list) the target namespace that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] uses to determine the schema to process the received message with.</span></span>  
  
6. <span data-ttu-id="85cc3-119">单击**Apply**以接受更改，或单击**确定**以输入和验证所做的更改，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="85cc3-119">Click **Apply** to accept the changes, or click **OK** to enter and validate the changes, and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85cc3-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="85cc3-120">See Also</span></span>  
 [<span data-ttu-id="85cc3-121">为事务集设置配置 X12 后备协议属性</span><span class="sxs-lookup"><span data-stu-id="85cc3-121">Configuring X12 Fallback Agreement Properties for Transaction Set Settings</span></span>](../core/configuring-x12-fallback-agreement-properties-for-transaction-set-settings.md)