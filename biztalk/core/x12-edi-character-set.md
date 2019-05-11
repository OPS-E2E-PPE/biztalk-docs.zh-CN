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
ms.openlocfilehash: b6fb92d0b8a20e9ca4e1a71aead55af21b1daeea
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394785"
---
# <a name="x12-edi-character-set"></a><span data-ttu-id="d1496-102">X12 EDI 字符集</span><span class="sxs-lookup"><span data-stu-id="d1496-102">X12 EDI Character Set</span></span>
<span data-ttu-id="d1496-103">使用 Ñ 字符或重读符号 （'） 时，指定以下项：</span><span class="sxs-lookup"><span data-stu-id="d1496-103">When using the Ñ character or a grave accent (\`), specify the following:</span></span>  


|                                                                   |                                  <span data-ttu-id="d1496-104">字符集</span><span class="sxs-lookup"><span data-stu-id="d1496-104">Character Set</span></span>                                   |
|-------------------------------------------------------------------|----------------------------------------------------------------------------------|
|             <span data-ttu-id="d1496-105">仅 Ñ EDI 文档中的字符</span><span class="sxs-lookup"><span data-stu-id="d1496-105">Only the Ñ character in the EDI document</span></span>              |                            <span data-ttu-id="d1496-106">使用扩展的字符集</span><span class="sxs-lookup"><span data-stu-id="d1496-106">Use Extended Character Set</span></span>                            |
|           <span data-ttu-id="d1496-107">抑音符 (\`) 中的 EDI 文档 |                             使用 UTF8 字符集</span><span class="sxs-lookup"><span data-stu-id="d1496-107">Only a grave accent (\`) in the EDI document            |                              Use UTF8 Character Set</span></span>                              |
| <span data-ttu-id="d1496-108">Ñ 字符**并**抑音符 (\`) 在同一文档中: | 的入站的文档必须具有 UTF8 编码</span><span class="sxs-lookup"><span data-stu-id="d1496-108">The Ñ character **and** a grave accent (\`) in the same document: | -   The inbound document must have UTF8 encoding</span></span><br /><span data-ttu-id="d1496-109">-使用 UTF8 字符集</span><span class="sxs-lookup"><span data-stu-id="d1496-109">-   Use UTF8 Character Set</span></span> |

 <span data-ttu-id="d1496-110">以下链接提供了有关 EDI 字符集的详细信息：</span><span class="sxs-lookup"><span data-stu-id="d1496-110">The following links provider more information on EDI Character Sets:</span></span>  

 [<span data-ttu-id="d1496-111">EDI 字符集</span><span class="sxs-lookup"><span data-stu-id="d1496-111">EDI Character Sets</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=271249)  

 [<span data-ttu-id="d1496-112">EDI 字符集支持</span><span class="sxs-lookup"><span data-stu-id="d1496-112">EDI Character Set Support</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=271250)