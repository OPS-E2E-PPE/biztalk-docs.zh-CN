---
title: "配置回退信封属性 （X12 事务集设置） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2a951f70-07d5-4a58-b1ea-e7117a45c545
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7aa7898d1e1a83da879400a89d5cd089ef2d4069
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-fallback-envelope-properties-x12-transaction-set-settings"></a><span data-ttu-id="1fd12-102">配置回退信封属性（X 12 事务集设置）</span><span class="sxs-lookup"><span data-stu-id="1fd12-102">Configuring Fallback Envelope Properties (X12-Transaction Set Settings)</span></span>
<span data-ttu-id="1fd12-103">在**包络线**页**事务设置设置**部分中，你定义 BizTalk Server 如何生成它将发送到方的 X12 编码交换的 GS 段。</span><span class="sxs-lookup"><span data-stu-id="1fd12-103">In the **Envelopes** page of the **Transaction Set Settings** section, you define how BizTalk Server generates the GS segments for an X12-encoded interchange that it sends to the party.</span></span> <span data-ttu-id="1fd12-104">GS 段为 X12 编码的交换标识和指定功能组。</span><span class="sxs-lookup"><span data-stu-id="1fd12-104">A GS segment identifies and specifies a functional group for an X12-encoded interchange.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1fd12-105">本主题还适用于与 HIPAA 相关的设置。</span><span class="sxs-lookup"><span data-stu-id="1fd12-105">This topic applies also to HIPAA-related settings.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="1fd12-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="1fd12-106">Prerequisites</span></span>  
 <span data-ttu-id="1fd12-107">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="1fd12-107">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-define-the-gs-segments"></a><span data-ttu-id="1fd12-108">定义 GS 段</span><span class="sxs-lookup"><span data-stu-id="1fd12-108">To define the GS segments</span></span>  
  
1.  <span data-ttu-id="1fd12-109">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**方**节点，，然后单击**X12 回退设置**。</span><span class="sxs-lookup"><span data-stu-id="1fd12-109">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Parties** node, and then click **X12 Fallback Settings**.</span></span>  
  
2.  <span data-ttu-id="1fd12-110">在**X12 回退设置**对话框中，在**X12 协议页**选项卡上，在**事务设置设置**部分中，单击**包络线**.</span><span class="sxs-lookup"><span data-stu-id="1fd12-110">In the **X12 Fallback Settings** dialog box, in the **X12 Agreement Pages** tab, under the **Transaction Set Settings** section, click **Envelopes**.</span></span>  
  
3.  <span data-ttu-id="1fd12-111">有关**功能代码 (GS01)**，从下拉列表中选择一个值。</span><span class="sxs-lookup"><span data-stu-id="1fd12-111">For **Functional code (GS01)**, select a value from the drop-down list.</span></span>  
  
4.  <span data-ttu-id="1fd12-112">有关**应用程序发件人 (GS02)**，输入一个字母数字值，该值最少包含 2，最多 15 个。</span><span class="sxs-lookup"><span data-stu-id="1fd12-112">For **Application sender (GS02)**, enter an alphanumeric value with a minimum of 2 and a maximum of 15.</span></span> <span data-ttu-id="1fd12-113">这是必填字段。</span><span class="sxs-lookup"><span data-stu-id="1fd12-113">This is a required field.</span></span>  
  
5.  <span data-ttu-id="1fd12-114">有关**应用程序接收方 (GS03)**，输入一个字母数字值，该值最少包含 2，最多 15 个。</span><span class="sxs-lookup"><span data-stu-id="1fd12-114">For **Application receiver (GS03)**, enter an alphanumeric value with a minimum of 2 and a maximum of 15.</span></span> <span data-ttu-id="1fd12-115">这是必填字段。</span><span class="sxs-lookup"><span data-stu-id="1fd12-115">This is a required field.</span></span>  
  
6.  <span data-ttu-id="1fd12-116">有关**日期格式 (GS04)**，从下拉列表中选择 CCYYMMDD 或 YYMMDD。</span><span class="sxs-lookup"><span data-stu-id="1fd12-116">For **Date format (GS04)**, select CCYYMMDD or YYMMDD from the drop-down list.</span></span> <span data-ttu-id="1fd12-117">这是必填字段。</span><span class="sxs-lookup"><span data-stu-id="1fd12-117">This is a required field.</span></span>  
  
7.  <span data-ttu-id="1fd12-118">有关**时间格式 (GS05)**，从下拉列表中选择 HHMM、 HHMMSS 或 HHMMSSdd。</span><span class="sxs-lookup"><span data-stu-id="1fd12-118">For **Time format (GS05)**, select HHMM, HHMMSS, or HHMMSSdd from the drop-down list.</span></span> <span data-ttu-id="1fd12-119">这是必填字段。</span><span class="sxs-lookup"><span data-stu-id="1fd12-119">This is a required field.</span></span>  
  
8.  <span data-ttu-id="1fd12-120">有关**责任代理 (GS07)**，从下拉列表中选择值。</span><span class="sxs-lookup"><span data-stu-id="1fd12-120">For **Responsible agency (GS07)**, select the value from the drop-down list.</span></span>  
  
9. <span data-ttu-id="1fd12-121">有关**文档标识符 (GS08)**，输入一个字母数字值，该值最小为 1，最大为 12。</span><span class="sxs-lookup"><span data-stu-id="1fd12-121">For **Document identifier (GS08)**, enter an alphanumeric value with a minimum of 1 and a maximum of 12.</span></span> <span data-ttu-id="1fd12-122">此字段为可选字段。</span><span class="sxs-lookup"><span data-stu-id="1fd12-122">This is an optional field.</span></span>  
  
10. <span data-ttu-id="1fd12-123">单击**应用**接受所做的更改，然后才能继续进行配置，或单击**确定**验证所做的更改，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="1fd12-123">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fd12-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1fd12-124">See Also</span></span>  
 [<span data-ttu-id="1fd12-125">配置 X12 事务的回退协议属性设置</span><span class="sxs-lookup"><span data-stu-id="1fd12-125">Configuring X12 Fallback Agreement Properties for Transaction Set Settings</span></span>](../core/configuring-x12-fallback-agreement-properties-for-transaction-set-settings.md)