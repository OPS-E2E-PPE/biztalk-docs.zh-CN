---
title: "示例消息演示文稿 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- examples, SWIFT message block
- SWIFT messages, message block example
ms.assetid: 3136a7da-658d-4100-bbe5-2186ee8bafd1
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a14fe8cf93d0c657f2cebbdca3b2f9058f909982
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="sample-message-presentation"></a><span data-ttu-id="fd8f8-102">示例消息演示文稿</span><span class="sxs-lookup"><span data-stu-id="fd8f8-102">Sample Message Presentation</span></span>
<span data-ttu-id="fd8f8-103">下表显示 SWIFT 消息块布局的示例。</span><span class="sxs-lookup"><span data-stu-id="fd8f8-103">The following table shows an example of the block layout of a SWIFT message.</span></span>  
  
|<span data-ttu-id="fd8f8-104">分块</span><span class="sxs-lookup"><span data-stu-id="fd8f8-104">Block</span></span>|<span data-ttu-id="fd8f8-105">示例</span><span class="sxs-lookup"><span data-stu-id="fd8f8-105">Example</span></span>|  
|-----------|-------------|  
|<span data-ttu-id="fd8f8-106">**阻止 1**基本标头</span><span class="sxs-lookup"><span data-stu-id="fd8f8-106">**Block 1** Basic Header</span></span>|<span data-ttu-id="fd8f8-107">{1:F01BCITITMMAXXX0012000123}</span><span class="sxs-lookup"><span data-stu-id="fd8f8-107">{1:F01BCITITMMAXXX0012000123}</span></span>|  
|<span data-ttu-id="fd8f8-108">**阻止 2** (I) 应用程序标头的输入 （SWIFT)</span><span class="sxs-lookup"><span data-stu-id="fd8f8-108">**Block 2** (I) Application Header Input (to SWIFT)</span></span><br /><br /> <span data-ttu-id="fd8f8-109">或</span><span class="sxs-lookup"><span data-stu-id="fd8f8-109">Or</span></span><br /><br /> <span data-ttu-id="fd8f8-110">**阻止 2** （从 SWIFT) (O) 应用程序标头输出</span><span class="sxs-lookup"><span data-stu-id="fd8f8-110">**Block 2** (O) Application Header Output (from SWIFT)</span></span>|<span data-ttu-id="fd8f8-111">{2:I103VBOEATWWXXXXN}或者 {2:O1030840010605BNPAFRPPAXXX00120078960106051051U3</span><span class="sxs-lookup"><span data-stu-id="fd8f8-111">{2:I103VBOEATWWXXXXN} Or {2:O1030840010605BNPAFRPPAXXX00120078960106051051U3</span></span>|  
|<span data-ttu-id="fd8f8-112">**块 3**用户标头</span><span class="sxs-lookup"><span data-stu-id="fd8f8-112">**Block 3** User Header</span></span>|<span data-ttu-id="fd8f8-113">{3: {108:BCITITMMA950906}}</span><span class="sxs-lookup"><span data-stu-id="fd8f8-113">{3:{108:BCITITMMA950906}}</span></span>|  
|<span data-ttu-id="fd8f8-114">**阻止 4**文本</span><span class="sxs-lookup"><span data-stu-id="fd8f8-114">**Block 4** Text</span></span>|<span data-ttu-id="fd8f8-115">{4:\<CRLF >: 20:1234567890\<CRLF >: 23B:CRED\<CRLF >: 32A:010605GBP45000，\<CRLF >: 33B:GBP45000，\<CRLF >: 50K:MASTERS 导入\<CRLF > RUE DES ARBRES119\<CRLF > CAMBRAI\<CRLF >: 52A:BNPAFRPPCAM\<CRLF >: 53A:POCIITMM680\<CRLF >: 57A:BCITITMM680\<CRLF >: 59: / P03452032022819 30\<CRLF > 总计导入\<CRLF > PESCARA\<CRLF >: 70: / RFB/清单 5591\<CRLF >: 71A:SHA\<CRLF >-}</span><span class="sxs-lookup"><span data-stu-id="fd8f8-115">{4:\<CRLF> :20:1234567890\<CRLF> :23B:CRED\<CRLF> :32A:010605GBP45000,\<CRLF> :33B:GBP45000,\<CRLF> :50K:MASTERS IMPORT\<CRLF> RUE DES ARBRES 119\<CRLF> CAMBRAI\<CRLF> :52A:BNPAFRPPCAM\<CRLF> :53A:POCIITMM680\<CRLF> :57A:BCITITMM680\<CRLF> :59:/P03452032022819 30\<CRLF> GRAND IMPORT\<CRLF> PESCARA\<CRLF> :70:/RFB/INV 5591\<CRLF> :71A:SHA\<CRLF> -}</span></span>|  
|<span data-ttu-id="fd8f8-116">**阻止 5**拖车安排</span><span class="sxs-lookup"><span data-stu-id="fd8f8-116">**Block 5** Trailers</span></span>|<span data-ttu-id="fd8f8-117">{5: {MAC: 12345678} {CHK:123456789ABC}}</span><span class="sxs-lookup"><span data-stu-id="fd8f8-117">{5:{MAC:12345678}{CHK:123456789ABC}}</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fd8f8-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fd8f8-118">See Also</span></span>  
 [<span data-ttu-id="fd8f8-119">SWIFT 架构</span><span class="sxs-lookup"><span data-stu-id="fd8f8-119">SWIFT Schemas</span></span>](../../adapters-and-accelerators/accelerator-swift/swift-schemas.md)