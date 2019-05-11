---
title: AS2 解码器处理失败，因为 MDN 指示 AS2 消息处理失败 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2bce620a-f336-435e-b7c3-3db060f2819d
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c2507c1eafa258335302f4670f612db1b213e82
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389011"
---
# <a name="the-as2-decoder-failed-processing-because-the-mdn-indicated-the-as2-message-failed-processing"></a><span data-ttu-id="00df3-102">AS2 解码器处理失败，因为 MDN 指示 AS2 消息处理失败</span><span class="sxs-lookup"><span data-stu-id="00df3-102">The AS2 Decoder failed processing because the MDN indicated the AS2 message failed processing</span></span>
## <a name="details"></a><span data-ttu-id="00df3-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="00df3-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                  |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="00df3-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="00df3-104">Product Name</span></span>   |                                                                [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                |
| <span data-ttu-id="00df3-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="00df3-105">Product Version</span></span> |                                                                            [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                            |
|    <span data-ttu-id="00df3-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="00df3-106">Event ID</span></span>     |                                                                                                        -                                                                                                         |
|  <span data-ttu-id="00df3-107">事件源</span><span class="sxs-lookup"><span data-stu-id="00df3-107">Event Source</span></span>   |                                                              [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="00df3-108">EDI</span><span class="sxs-lookup"><span data-stu-id="00df3-108">EDI</span></span>                                                              |
|    <span data-ttu-id="00df3-109">组件</span><span class="sxs-lookup"><span data-stu-id="00df3-109">Component</span></span>    |                                                                                                    <span data-ttu-id="00df3-110">AS2 引擎</span><span class="sxs-lookup"><span data-stu-id="00df3-110">AS2 Engine</span></span>                                                                                                    |
|  <span data-ttu-id="00df3-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="00df3-111">Symbolic Name</span></span>  |                                                                                      <span data-ttu-id="00df3-112">AS2DecoderMdnProcessingFailureReturned</span><span class="sxs-lookup"><span data-stu-id="00df3-112">AS2DecoderMdnProcessingFailureReturned</span></span>                                                                                      |
|  <span data-ttu-id="00df3-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="00df3-113">Message Text</span></span>   | <span data-ttu-id="00df3-114">AS2 解码器处理失败，因为 MDN 指示 AS2 消息处理失败。</span><span class="sxs-lookup"><span data-stu-id="00df3-114">The AS2 Decoder failure processing because the MDN indicated the AS2 message failed processing.</span></span>  <span data-ttu-id="00df3-115">MDN 消息的详细信息如下所示：AS2-从:"{0}"AS2-到:"{1}"MessageID:"{2}"OriginalMessageID:"{3}"</span><span class="sxs-lookup"><span data-stu-id="00df3-115">Details of the MDN message are as follows:  AS2-From:"{0}" AS2-To:"{1}" MessageID:"{2}" OriginalMessageID:"{3}"</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="00df3-116">解释</span><span class="sxs-lookup"><span data-stu-id="00df3-116">Explanation</span></span>  
 <span data-ttu-id="00df3-117">此错误/警告/信息事件表明 MDN 响应显示原始 AS2 消息接收方无法处理原始 AS2 消息。</span><span class="sxs-lookup"><span data-stu-id="00df3-117">This Error/Warning/Information event indicates that the MDN response shows that the receiver of the original AS2 message could not process the original AS2 message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="00df3-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="00df3-118">User Action</span></span>  
 <span data-ttu-id="00df3-119">若要解决此错误，请联系的 AS2 消息接收方、 确定在接收方处理失败的原因、 修复原始 AS2 消息，然后重新发送。</span><span class="sxs-lookup"><span data-stu-id="00df3-119">To resolve this error, contact the receiver of the AS2 message, determine why processing failed at the receiver, fix the original AS2 message, and then resend.</span></span>