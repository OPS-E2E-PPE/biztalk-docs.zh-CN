---
title: 配置回退信封属性 （X12-交换设置） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0e9b05ea-2a0f-42d6-adc2-c1f1f2b7a993
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8a6e7af661992db4067bd62d53b58322c486ec57
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65355669"
---
# <a name="configuring-fallback-envelope-properties-x12-interchange-settings"></a><span data-ttu-id="8a162-102">配置回退信封属性（X 12 交换设置）</span><span class="sxs-lookup"><span data-stu-id="8a162-102">Configuring Fallback Envelope Properties (X12-Interchange Settings)</span></span>
<span data-ttu-id="8a162-103">X12 交换信封生成设置定义如何[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]生成要发送到接收方的 X12 编码交换的信封。</span><span class="sxs-lookup"><span data-stu-id="8a162-103">X12 interchange envelope generation settings define how [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] generates the envelope of an X12-encoded interchange to be sent to the receiving party.</span></span> <span data-ttu-id="8a162-104">在此备用协议中，您将定义如何[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]生成在它发送到参与方的 X12 编码交换的 ISA 段。</span><span class="sxs-lookup"><span data-stu-id="8a162-104">In this fallback agreement, you define how [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] generates the ISA segment for an X12-encoded interchange that it sends to the party.</span></span> <span data-ttu-id="8a162-105">ISA 段是 X12 编码交换的交换控制标头。</span><span class="sxs-lookup"><span data-stu-id="8a162-105">An ISA segment is the interchange control header for an X12-encoded interchange.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8a162-106">有关[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]字母数字 ISA 字段的长度固定的运行时。</span><span class="sxs-lookup"><span data-stu-id="8a162-106">For the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] runtime, the length of alphanumeric ISA fields is fixed.</span></span> <span data-ttu-id="8a162-107">但是，对于[!INCLUDE[TPM](../includes/tpm-md.md)]用户界面，则可以为字母数字 ISA 字段输入单个字符。</span><span class="sxs-lookup"><span data-stu-id="8a162-107">However, for the [!INCLUDE[TPM](../includes/tpm-md.md)] user interface, you may enter a single character for an alphanumeric ISA field.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="8a162-108">将填充这些字段用尾随空格字符，以确保符合标准要求。</span><span class="sxs-lookup"><span data-stu-id="8a162-108">will pad these fields with trailing space characters to ensure compliance with standards requirements.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="8a162-109">此处所述的设置也适用于 HIPAA 交换信封生成。</span><span class="sxs-lookup"><span data-stu-id="8a162-109">The settings described here also apply to HIPAA interchange envelope generation.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="8a162-110">先决条件</span><span class="sxs-lookup"><span data-stu-id="8a162-110">Prerequisites</span></span>  
 <span data-ttu-id="8a162-111">必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。</span><span class="sxs-lookup"><span data-stu-id="8a162-111">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-define-the-envelope"></a><span data-ttu-id="8a162-112">若要定义信封</span><span class="sxs-lookup"><span data-stu-id="8a162-112">To define the envelope</span></span>  
  
1. <span data-ttu-id="8a162-113">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**方**节点，，然后单击**X12 后备设置**。</span><span class="sxs-lookup"><span data-stu-id="8a162-113">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Parties** node, and then click **X12 Fallback Settings**.</span></span>  
  
2. <span data-ttu-id="8a162-114">在中**X12 后备设置**对话框中**X12 协议页**选项卡上，在**交换设置**部分中，单击**信封**.</span><span class="sxs-lookup"><span data-stu-id="8a162-114">In the **X12 Fallback Settings** dialog box, in the **X12 Agreement Pages** tab, under the **Interchange Settings** section, click **Envelopes**.</span></span>  
  
3. <span data-ttu-id="8a162-115">下**ISA11 用法**，保留**标准标识符**选择指定一个标准标识符而不是重复分隔符，并从下拉列表中选择标准标识符的值。</span><span class="sxs-lookup"><span data-stu-id="8a162-115">Under **ISA11 usage**, keep **Standard identifier** selected to specify a standard identifier instead of a repetition separator, and then select a value for the standard identifier from the drop-down list.</span></span> <span data-ttu-id="8a162-116">选择**重复分隔符**若要指定重复分隔符而非标准标识符，然后再为此重复分隔符输入单个字符。</span><span class="sxs-lookup"><span data-stu-id="8a162-116">Select **Repetition separator** to specify a repetition separator instead of a standard identifier, and then enter a single character for the repetition separator.</span></span> <span data-ttu-id="8a162-117">用于分隔事务集内重复的段的重复分隔符仅限于 ASCII 字符集中的值。</span><span class="sxs-lookup"><span data-stu-id="8a162-117">The repetition separator, which is used to separate segments that repeat within a transaction set, is limited to the values in the ASCII character set.</span></span>  
  
4. <span data-ttu-id="8a162-118">有关**控制版本号 (ISA12)**，选择的 x12 标准，供版本[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]用于生成传出交换。</span><span class="sxs-lookup"><span data-stu-id="8a162-118">For **Control version number (ISA12)**, select the version of the X12 standard to be used by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] for generating an outgoing interchange.</span></span>  
  
5. <span data-ttu-id="8a162-119">有关**用法指示符 (ISA15)**，选择以指示生成的交换[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]是信息、 生产数据还是测试数据。</span><span class="sxs-lookup"><span data-stu-id="8a162-119">For **Usage indicator (ISA15)**, select to indicate whether an interchange generated by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is information, production data, or test data.</span></span>  
  
6. <span data-ttu-id="8a162-120">单击**Apply**以接受更改，然后才能继续进行配置，或单击**确定**以验证所做的更改，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="8a162-120">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a162-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="8a162-121">See Also</span></span>  
 [<span data-ttu-id="8a162-122">为交换处理配置 X12 后备协议属性</span><span class="sxs-lookup"><span data-stu-id="8a162-122">Configuring X12 Fallback Agreement Properties for Interchange Processing</span></span>](../core/configuring-x12-fallback-agreement-properties-for-interchange-processing.md)