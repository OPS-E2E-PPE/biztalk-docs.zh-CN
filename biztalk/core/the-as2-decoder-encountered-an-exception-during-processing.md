---
title: AS2 解码器过程中遇到异常处理 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b5f16d2e-e83c-4e2c-84be-41b5ed012dce
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2826a938a4f081b8c5895da809e9f16966e25834
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278317"
---
# <a name="the-as2-decoder-encountered-an-exception-during-processing"></a><span data-ttu-id="94dae-102">AS2 解码器在处理期间遇到异常</span><span class="sxs-lookup"><span data-stu-id="94dae-102">The AS2 Decoder encountered an exception during processing</span></span>
## <a name="details"></a><span data-ttu-id="94dae-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="94dae-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="94dae-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="94dae-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="94dae-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="94dae-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="94dae-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="94dae-106">Event ID</span></span>|-|  
|<span data-ttu-id="94dae-107">事件源</span><span class="sxs-lookup"><span data-stu-id="94dae-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="94dae-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="94dae-108"> EDI</span></span>|  
|<span data-ttu-id="94dae-109">组件</span><span class="sxs-lookup"><span data-stu-id="94dae-109">Component</span></span>|<span data-ttu-id="94dae-110">AS2 引擎</span><span class="sxs-lookup"><span data-stu-id="94dae-110">AS2 Engine</span></span>|  
|<span data-ttu-id="94dae-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="94dae-111">Symbolic Name</span></span>|<span data-ttu-id="94dae-112">AS2DecoderExceptionEncounteredDuringProcessing</span><span class="sxs-lookup"><span data-stu-id="94dae-112">AS2DecoderExceptionEncounteredDuringProcessing</span></span>|  
|<span data-ttu-id="94dae-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="94dae-113">Message Text</span></span>|<span data-ttu-id="94dae-114">AS2 解码器在处理期间遇到异常。</span><span class="sxs-lookup"><span data-stu-id="94dae-114">The AS2 Decoder encountered an exception during processing.</span></span>  <span data-ttu-id="94dae-115">消息和异常的详细信息如下所示： AS2-从:"{0}"AS2-到:"\ {1 \}"MessageID:"\ {2 \}"MessageType:"{3}"异常:"\ {4\}"</span><span class="sxs-lookup"><span data-stu-id="94dae-115">Details of the message and exception are as follows:  AS2-From:"{0}" AS2-To:"{1}" MessageID:"{2}" MessageType: "{3}" Exception:"{4}"</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="94dae-116">解释</span><span class="sxs-lookup"><span data-stu-id="94dae-116">Explanation</span></span>  
 <span data-ttu-id="94dae-117">此错误/警告/信息事件表明由于 AS2 解码器有问题，接收管道无法处理传入的 AS2 消息。</span><span class="sxs-lookup"><span data-stu-id="94dae-117">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming AS2 message because of an issue with the AS2 Decoder.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="94dae-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="94dae-118">User Action</span></span>  
 <span data-ttu-id="94dae-119">若要解决此错误，请通过检查 AS2 错误代码来确定错误条件的性质。</span><span class="sxs-lookup"><span data-stu-id="94dae-119">To resolve this error, determine the nature of the error condition by checking the AS2 error code.</span></span> <span data-ttu-id="94dae-120">有关 AS2 错误代码的详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助文件中的“AS2 错误代码”主题。</span><span class="sxs-lookup"><span data-stu-id="94dae-120">For more information on AS2 error codes, see the "AS2 Error Codes" topic in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] help file.</span></span>