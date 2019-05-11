---
title: 配置回退信封属性 （X12-事务集设置） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2a951f70-07d5-4a58-b1ea-e7117a45c545
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: afb2f0244f0f0ace3ebd2bba67909935a1e8e96b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391242"
---
# <a name="configuring-fallback-envelope-properties-x12-transaction-set-settings"></a><span data-ttu-id="179e5-102">配置回退信封属性（X 12 事务集设置）</span><span class="sxs-lookup"><span data-stu-id="179e5-102">Configuring Fallback Envelope Properties (X12-Transaction Set Settings)</span></span>
<span data-ttu-id="179e5-103">在中**信封**页**事务集设置**部分中，可以定义 BizTalk Server 如何生成它发送到参与方的 X12 编码交换的 GS 段。</span><span class="sxs-lookup"><span data-stu-id="179e5-103">In the **Envelopes** page of the **Transaction Set Settings** section, you define how BizTalk Server generates the GS segments for an X12-encoded interchange that it sends to the party.</span></span> <span data-ttu-id="179e5-104">GS 段标识，并指定功能组对于 X12 编码的交换。</span><span class="sxs-lookup"><span data-stu-id="179e5-104">A GS segment identifies and specifies a functional group for an X12-encoded interchange.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="179e5-105">本主题还适用于与 HIPAA 相关的设置。</span><span class="sxs-lookup"><span data-stu-id="179e5-105">This topic applies also to HIPAA-related settings.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="179e5-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="179e5-106">Prerequisites</span></span>  
 <span data-ttu-id="179e5-107">必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。</span><span class="sxs-lookup"><span data-stu-id="179e5-107">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-define-the-gs-segments"></a><span data-ttu-id="179e5-108">定义 GS 段</span><span class="sxs-lookup"><span data-stu-id="179e5-108">To define the GS segments</span></span>  
  
1. <span data-ttu-id="179e5-109">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**方**节点，，然后单击**X12 后备设置**。</span><span class="sxs-lookup"><span data-stu-id="179e5-109">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Parties** node, and then click **X12 Fallback Settings**.</span></span>  
  
2. <span data-ttu-id="179e5-110">在中**X12 后备设置**对话框中**X12 协议页**选项卡上，在**事务集设置**部分中，单击**信封**.</span><span class="sxs-lookup"><span data-stu-id="179e5-110">In the **X12 Fallback Settings** dialog box, in the **X12 Agreement Pages** tab, under the **Transaction Set Settings** section, click **Envelopes**.</span></span>  
  
3. <span data-ttu-id="179e5-111">有关**功能代码 (GS01)**，从下拉列表中选择一个值。</span><span class="sxs-lookup"><span data-stu-id="179e5-111">For **Functional code (GS01)**, select a value from the drop-down list.</span></span>  
  
4. <span data-ttu-id="179e5-112">有关**应用程序发送方 (GS02)**，输入最小为 2、 最大为 15 的字母数字值。</span><span class="sxs-lookup"><span data-stu-id="179e5-112">For **Application sender (GS02)**, enter an alphanumeric value with a minimum of 2 and a maximum of 15.</span></span> <span data-ttu-id="179e5-113">这是必填字段。</span><span class="sxs-lookup"><span data-stu-id="179e5-113">This is a required field.</span></span>  
  
5. <span data-ttu-id="179e5-114">有关**应用程序接收方 (GS03)**，输入最小为 2、 最大为 15 的字母数字值。</span><span class="sxs-lookup"><span data-stu-id="179e5-114">For **Application receiver (GS03)**, enter an alphanumeric value with a minimum of 2 and a maximum of 15.</span></span> <span data-ttu-id="179e5-115">这是必填字段。</span><span class="sxs-lookup"><span data-stu-id="179e5-115">This is a required field.</span></span>  
  
6. <span data-ttu-id="179e5-116">有关**日期格式 (GS04)**，从下拉列表中选择 CCYYMMDD 或 YYMMDD。</span><span class="sxs-lookup"><span data-stu-id="179e5-116">For **Date format (GS04)**, select CCYYMMDD or YYMMDD from the drop-down list.</span></span> <span data-ttu-id="179e5-117">这是必填字段。</span><span class="sxs-lookup"><span data-stu-id="179e5-117">This is a required field.</span></span>  
  
7. <span data-ttu-id="179e5-118">有关**时间格式 (GS05)**，从下拉列表中选择 HHMM、 HHMMSS 或 HHMMSSdd。</span><span class="sxs-lookup"><span data-stu-id="179e5-118">For **Time format (GS05)**, select HHMM, HHMMSS, or HHMMSSdd from the drop-down list.</span></span> <span data-ttu-id="179e5-119">这是必填字段。</span><span class="sxs-lookup"><span data-stu-id="179e5-119">This is a required field.</span></span>  
  
8. <span data-ttu-id="179e5-120">有关**责任代理 (GS07)**，从下拉列表中选择值。</span><span class="sxs-lookup"><span data-stu-id="179e5-120">For **Responsible agency (GS07)**, select the value from the drop-down list.</span></span>  
  
9. <span data-ttu-id="179e5-121">有关**文档标识符 (GS08)**，输入最小为 1 和最大为 12 的字母数字值。</span><span class="sxs-lookup"><span data-stu-id="179e5-121">For **Document identifier (GS08)**, enter an alphanumeric value with a minimum of 1 and a maximum of 12.</span></span> <span data-ttu-id="179e5-122">这是一个可选字段。</span><span class="sxs-lookup"><span data-stu-id="179e5-122">This is an optional field.</span></span>  
  
10. <span data-ttu-id="179e5-123">单击**Apply**以接受更改，然后才能继续进行配置，或单击**确定**以验证所做的更改，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="179e5-123">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="179e5-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="179e5-124">See Also</span></span>  
 [<span data-ttu-id="179e5-125">为事务集设置配置 X12 后备协议属性</span><span class="sxs-lookup"><span data-stu-id="179e5-125">Configuring X12 Fallback Agreement Properties for Transaction Set Settings</span></span>](../core/configuring-x12-fallback-agreement-properties-for-transaction-set-settings.md)