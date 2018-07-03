---
title: X12 EDI 字符集 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 76e7b327-b0bd-4f16-8bfe-6c0184059f2b
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9bd501c81b92f4fa7824009a949fd6c7e58eaf3b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023099"
---
# <a name="x12-edi-character-set"></a><span data-ttu-id="f1798-102">X12 EDI 字符集</span><span class="sxs-lookup"><span data-stu-id="f1798-102">X12 EDI Character Set</span></span>
<span data-ttu-id="f1798-103">使用 Ñ 字符或重读符号 （'） 时，指定以下项：</span><span class="sxs-lookup"><span data-stu-id="f1798-103">When using the Ñ character or a grave accent (\`), specify the following:</span></span>  


|                                                                   |                                  <span data-ttu-id="f1798-104">字符集</span><span class="sxs-lookup"><span data-stu-id="f1798-104">Character Set</span></span>                                   |
|-------------------------------------------------------------------|----------------------------------------------------------------------------------|
|             <span data-ttu-id="f1798-105">仅 Ñ EDI 文档中的字符</span><span class="sxs-lookup"><span data-stu-id="f1798-105">Only the Ñ character in the EDI document</span></span>              |                            <span data-ttu-id="f1798-106">使用扩展字符集</span><span class="sxs-lookup"><span data-stu-id="f1798-106">Use Extended Character Set</span></span>                            |
|           <span data-ttu-id="f1798-107">抑音符 (\`) EDI 文档中</span><span class="sxs-lookup"><span data-stu-id="f1798-107">Only a grave accent (\`) in the EDI document</span></span>            |                              <span data-ttu-id="f1798-108">使用 UTF8 字符集</span><span class="sxs-lookup"><span data-stu-id="f1798-108">Use UTF8 Character Set</span></span>                              |
| <span data-ttu-id="f1798-109">Ñ 字符**并**抑音符 (\`) 在同一文档中：</span><span class="sxs-lookup"><span data-stu-id="f1798-109">The Ñ character **and** a grave accent (\`) in the same document:</span></span> | <span data-ttu-id="f1798-110">-入站的文档必须具有 UTF8 编码</span><span class="sxs-lookup"><span data-stu-id="f1798-110">-   The inbound document must have UTF8 encoding</span></span><br /><span data-ttu-id="f1798-111">-使用 UTF8 字符集</span><span class="sxs-lookup"><span data-stu-id="f1798-111">-   Use UTF8 Character Set</span></span> |

 <span data-ttu-id="f1798-112">以下链接提供了有关 EDI 字符集的详细信息：</span><span class="sxs-lookup"><span data-stu-id="f1798-112">The following links provider more information on EDI Character Sets:</span></span>  

 [<span data-ttu-id="f1798-113">EDI 字符集</span><span class="sxs-lookup"><span data-stu-id="f1798-113">EDI Character Sets</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=271249)  

 [<span data-ttu-id="f1798-114">EDI 字符集支持</span><span class="sxs-lookup"><span data-stu-id="f1798-114">EDI Character Set Support</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=271250)