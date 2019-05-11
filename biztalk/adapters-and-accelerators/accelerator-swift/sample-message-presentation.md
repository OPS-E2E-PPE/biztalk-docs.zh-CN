---
title: 示例消息演示文稿 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, SWIFT message block
- SWIFT messages, message block example
ms.assetid: 3136a7da-658d-4100-bbe5-2186ee8bafd1
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4223127d483ee4ded16e657a1214161e7f8b6791
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530096"
---
# <a name="sample-message-presentation"></a><span data-ttu-id="475f0-102">示例消息演示文稿</span><span class="sxs-lookup"><span data-stu-id="475f0-102">Sample Message Presentation</span></span>
<span data-ttu-id="475f0-103">下表显示了 SWIFT 消息的块状布局的示例。</span><span class="sxs-lookup"><span data-stu-id="475f0-103">The following table shows an example of the block layout of a SWIFT message.</span></span>  
  
|<span data-ttu-id="475f0-104">分块</span><span class="sxs-lookup"><span data-stu-id="475f0-104">Block</span></span>|<span data-ttu-id="475f0-105">示例</span><span class="sxs-lookup"><span data-stu-id="475f0-105">Example</span></span>|  
|-----------|-------------|  
|<span data-ttu-id="475f0-106">**阻止 1**基本标头</span><span class="sxs-lookup"><span data-stu-id="475f0-106">**Block 1** Basic Header</span></span>|<span data-ttu-id="475f0-107">{1:F01BCITITMMAXXX0012000123}</span><span class="sxs-lookup"><span data-stu-id="475f0-107">{1:F01BCITITMMAXXX0012000123}</span></span>|  
|<span data-ttu-id="475f0-108">**阻止 2** (I) 应用程序标头的输入 （SWIFT)</span><span class="sxs-lookup"><span data-stu-id="475f0-108">**Block 2** (I) Application Header Input (to SWIFT)</span></span><br /><br /> <span data-ttu-id="475f0-109">或</span><span class="sxs-lookup"><span data-stu-id="475f0-109">Or</span></span><br /><br /> <span data-ttu-id="475f0-110">**阻止 2** (O) 应用程序标头输出 （从 SWIFT)</span><span class="sxs-lookup"><span data-stu-id="475f0-110">**Block 2** (O) Application Header Output (from SWIFT)</span></span>|<span data-ttu-id="475f0-111">{2:I103VBOEATWWXXXXN} Or {2:O1030840010605BNPAFRPPAXXX00120078960106051051U3</span><span class="sxs-lookup"><span data-stu-id="475f0-111">{2:I103VBOEATWWXXXXN} Or {2:O1030840010605BNPAFRPPAXXX00120078960106051051U3</span></span>|  
|<span data-ttu-id="475f0-112">**块 3**用户标头</span><span class="sxs-lookup"><span data-stu-id="475f0-112">**Block 3** User Header</span></span>|<span data-ttu-id="475f0-113">{3:{108:BCITITMMA950906}}</span><span class="sxs-lookup"><span data-stu-id="475f0-113">{3:{108:BCITITMMA950906}}</span></span>|  
|<span data-ttu-id="475f0-114">**阻止 4**文本</span><span class="sxs-lookup"><span data-stu-id="475f0-114">**Block 4** Text</span></span>|<span data-ttu-id="475f0-115">{4:\<CRLF\> : 20:1234567890\<CRLF\> : 23B:CRED\<CRLF\> : 32A:010605GBP45000，\<CRLF\> : 33B:GBP45000，\<CRLF\> : 50K:MASTERS 导入\<CRLF\> RUE DES ARBRES 119\<CRLF\> CAMBRAI\<CRLF\> : 52A:BNPAFRPPCAM\<CRLF\> : 53A:POCIITMM680\<CRLF\> : 57A:BCITITMM680\<CRLF\> : 59: / P03452032022819 30\<CRLF\> GRAND 导入\<CRLF\> PESCARA\<CRLF\> : 70: / RFB / INV 5591\<CRLF\> : 71A:SHA\<CRLF\> -}</span><span class="sxs-lookup"><span data-stu-id="475f0-115">{4:\<CRLF\> :20:1234567890\<CRLF\> :23B:CRED\<CRLF\> :32A:010605GBP45000,\<CRLF\> :33B:GBP45000,\<CRLF\> :50K:MASTERS IMPORT\<CRLF\> RUE DES ARBRES 119\<CRLF\> CAMBRAI\<CRLF\> :52A:BNPAFRPPCAM\<CRLF\> :53A:POCIITMM680\<CRLF\> :57A:BCITITMM680\<CRLF\> :59:/P03452032022819 30\<CRLF\> GRAND IMPORT\<CRLF\> PESCARA\<CRLF\> :70:/RFB/INV 5591\<CRLF\> :71A:SHA\<CRLF\> -}</span></span>|  
|<span data-ttu-id="475f0-116">**阻止 5**尾部</span><span class="sxs-lookup"><span data-stu-id="475f0-116">**Block 5** Trailers</span></span>|<span data-ttu-id="475f0-117">{5: {MAC: 12345678} {CHK:123456789ABC}}</span><span class="sxs-lookup"><span data-stu-id="475f0-117">{5:{MAC:12345678}{CHK:123456789ABC}}</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="475f0-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="475f0-118">See Also</span></span>  
 [<span data-ttu-id="475f0-119">SWIFT 架构</span><span class="sxs-lookup"><span data-stu-id="475f0-119">SWIFT Schemas</span></span>](../../adapters-and-accelerators/accelerator-swift/swift-schemas.md)