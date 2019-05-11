---
title: EDI 字符集支持 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c4f4492b-8cbe-48ed-810a-3e73e1cb5996
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5c38e7a8115be79d44e39cb4b1c60ef975219ad7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350459"
---
# <a name="edi-character-set-support"></a><span data-ttu-id="70295-102">EDI 字符集支持</span><span class="sxs-lookup"><span data-stu-id="70295-102">EDI Character Set Support</span></span>
<span data-ttu-id="70295-103">本主题指明 BizTalk Server EDI 功能中支持哪些字符集。</span><span class="sxs-lookup"><span data-stu-id="70295-103">This topic indicates which character sets are supported in the EDI features of BizTalk Server.</span></span>  
  
|<span data-ttu-id="70295-104">EDI 编码</span><span class="sxs-lookup"><span data-stu-id="70295-104">EDI Encoding</span></span>|<span data-ttu-id="70295-105">支持的字符集</span><span class="sxs-lookup"><span data-stu-id="70295-105">Supported Character Sets</span></span>|  
|------------------|------------------------------|  
|<span data-ttu-id="70295-106">X12 （包括 HIPAA）</span><span class="sxs-lookup"><span data-stu-id="70295-106">X12 (including HIPAA)</span></span>|<span data-ttu-id="70295-107">X12-基本字符集 （ASCII 的子集）</span><span class="sxs-lookup"><span data-stu-id="70295-107">X12 - Basic character set (subset of ASCII)</span></span>|  
|-|<span data-ttu-id="70295-108">X12 扩展字符集 (ASCII 的子集，还包括 ISO8859-1 个字符)</span><span class="sxs-lookup"><span data-stu-id="70295-108">X12- Extended character set (subset of ASCII and also includes ISO8859-1 chars)</span></span>|  
|-|<span data-ttu-id="70295-109">UTF8/UNICODE</span><span class="sxs-lookup"><span data-stu-id="70295-109">UTF8/UNICODE</span></span>|  
|<span data-ttu-id="70295-110">EDIFACT</span><span class="sxs-lookup"><span data-stu-id="70295-110">EDIFACT</span></span>|<span data-ttu-id="70295-111">UNOA</span><span class="sxs-lookup"><span data-stu-id="70295-111">UNOA</span></span>|  
|-|<span data-ttu-id="70295-112">UNOB</span><span class="sxs-lookup"><span data-stu-id="70295-112">UNOB</span></span>|  
|-|<span data-ttu-id="70295-113">UNOC-ISO 8859-1:信息处理-第 1 部分：拉丁字母表不能。</span><span class="sxs-lookup"><span data-stu-id="70295-113">UNOC- ISO 8859-1 : Information processing - Part 1: Latin alphabet No.</span></span> <span data-ttu-id="70295-114">1</span><span class="sxs-lookup"><span data-stu-id="70295-114">1</span></span>|  
|-|<span data-ttu-id="70295-115">KECA-KS_C_5601-1987年 （Windows 949 代码页）</span><span class="sxs-lookup"><span data-stu-id="70295-115">KECA - KS_C_5601-1987 (Windows 949 Code page)</span></span>|  
|-|<span data-ttu-id="70295-116">UNOX (ISO2022-JP)</span><span class="sxs-lookup"><span data-stu-id="70295-116">UNOX (ISO2022 – JP)</span></span>|  
|-|<span data-ttu-id="70295-117">UNOY-UTF8 编码数据**注意：** UNOD 到 UNOK 字符设置的支持 UTF8 编码的数据也受支持。</span><span class="sxs-lookup"><span data-stu-id="70295-117">UNOY- UTF8 encoded data **Note:**  The UNOD through UNOK character sets that support UTF8 encoded data are also supported.</span></span>|  
  
## <a name="setting-the-edi-character-set"></a><span data-ttu-id="70295-118">设置 EDI 字符集</span><span class="sxs-lookup"><span data-stu-id="70295-118">Setting the EDI Character Set</span></span>  
 <span data-ttu-id="70295-119">对于 X12 编码的交换，可以设置为管道通过设置 CharacterSet 管道属性设置的字符。</span><span class="sxs-lookup"><span data-stu-id="70295-119">For X12 encoded interchanges, you can set the character set for a pipeline by setting the CharacterSet pipeline property.</span></span> <span data-ttu-id="70295-120">有关详细信息，请参阅[配置 EDI 管道属性](../core/configuring-edi-pipeline-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="70295-120">For more information, see [Configuring EDI Pipeline Properties](../core/configuring-edi-pipeline-properties.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="70295-121">没有一个 X12 字符集控件在 X12 中的 EDI 属性对话框框中 BizTalk Server 管理控制台中，但此控件只用于验证的值的 X12 交换信封生成页输入中 EDI 的属性属性对话框。</span><span class="sxs-lookup"><span data-stu-id="70295-121">There is an X12 character set control in the X12 Interchange Envelope Generation page of the X12 EDI Properties dialog box in the BizTalk Server Administration console, but that control is only used to validate the values entered for the properties in the EDI Properties dialog box.</span></span>  
  
 <span data-ttu-id="70295-122">对于 EDIFACT 编码的交换，可以设置的字符集的参与方作为交换接收方的参与方的 UNB 段定义属性页中设置 UNB1.1 参与方属性。</span><span class="sxs-lookup"><span data-stu-id="70295-122">For EDIFACT encoded interchanges, you can set the character set for a party by setting the UNB1.1 party property in the UNB Segment Definition property page for the party as interchange receiver.</span></span> <span data-ttu-id="70295-123">将传入交换中使用的编码由交换标头中 UNB1.1 字段的值确定。</span><span class="sxs-lookup"><span data-stu-id="70295-123">The encoding used in an incoming interchange is determined by the value of the UNB1.1 field in the header of the interchange.</span></span> <span data-ttu-id="70295-124">有关详细信息，请参阅[配置信封 （EDIFACT-事务集设置）](../core/configuring-envelopes-edifact-transaction-set-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="70295-124">For more information, see [Configuring Envelopes (EDIFACT-Transaction Set Settings)](../core/configuring-envelopes-edifact-transaction-set-settings.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70295-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="70295-125">See Also</span></span>  
 <span data-ttu-id="70295-126">[配置 EDI 管道属性](../core/configuring-edi-pipeline-properties.md) </span><span class="sxs-lookup"><span data-stu-id="70295-126">[Configuring EDI Pipeline Properties](../core/configuring-edi-pipeline-properties.md) </span></span>  
 [<span data-ttu-id="70295-127">配置信封（EDIFACT-事务集设置）</span><span class="sxs-lookup"><span data-stu-id="70295-127">Configuring Envelopes (EDIFACT-Transaction Set Settings)</span></span>](../core/configuring-envelopes-edifact-transaction-set-settings.md)