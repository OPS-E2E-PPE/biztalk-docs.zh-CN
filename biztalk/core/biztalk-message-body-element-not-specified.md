---
title: "未指定 BizTalk 消息正文元素 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: af5d63c0-af96-4e34-828f-d29638cdf46d
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: baf79c8896169a06df66a8484377816c9897531e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="biztalk-message-body-element-not-specified"></a><span data-ttu-id="81c1b-102">未指定 BizTalk 消息正文元素</span><span class="sxs-lookup"><span data-stu-id="81c1b-102">BizTalk message body element not specified</span></span>
## <a name="details"></a><span data-ttu-id="81c1b-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="81c1b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="81c1b-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="81c1b-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="81c1b-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="81c1b-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="81c1b-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="81c1b-106">Event ID</span></span>|<span data-ttu-id="81c1b-107">0</span><span class="sxs-lookup"><span data-stu-id="81c1b-107">0</span></span>|  
|<span data-ttu-id="81c1b-108">事件源</span><span class="sxs-lookup"><span data-stu-id="81c1b-108">Event Source</span></span>|<span data-ttu-id="81c1b-109">0</span><span class="sxs-lookup"><span data-stu-id="81c1b-109">0</span></span>|  
|<span data-ttu-id="81c1b-110">组件</span><span class="sxs-lookup"><span data-stu-id="81c1b-110">Component</span></span>|<span data-ttu-id="81c1b-111">0</span><span class="sxs-lookup"><span data-stu-id="81c1b-111">0</span></span>|  
|<span data-ttu-id="81c1b-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="81c1b-112">Symbolic Name</span></span>|<span data-ttu-id="81c1b-113">0</span><span class="sxs-lookup"><span data-stu-id="81c1b-113">0</span></span>|  
|<span data-ttu-id="81c1b-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="81c1b-114">Message Text</span></span>|<span data-ttu-id="81c1b-115">未指定 BizTalk 消息正文元素</span><span class="sxs-lookup"><span data-stu-id="81c1b-115">BizTalk message body element not specified</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="81c1b-116">解释</span><span class="sxs-lookup"><span data-stu-id="81c1b-116">Explanation</span></span>  
 <span data-ttu-id="81c1b-117">此错误表示对出站 WCF 消息使用了模板选项。</span><span class="sxs-lookup"><span data-stu-id="81c1b-117">This error indicates the use of the template option for the outbound WCF message.</span></span> <span data-ttu-id="81c1b-118">但是，模板表达式不包含 BizTalk 消息正文元素。</span><span class="sxs-lookup"><span data-stu-id="81c1b-118">However, the template expression doesn’t contain the BizTalk message body element.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="81c1b-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="81c1b-119">User Action</span></span>  
 <span data-ttu-id="81c1b-120">确保模板表达式包含下列元素： \< **bts 消息正文 xmlns ="http://www.microsoft.com/schemas/bts2007"编码 ="[xml &#124; base64 &#124; 十六进制 &#124; 字符串]"/**>。</span><span class="sxs-lookup"><span data-stu-id="81c1b-120">Ensure that the template expression contains the following element: \<**bts-msg-body xmlns="http://www.microsoft.com/schemas/bts2007" encoding="[xml&#124;base64&#124;hex&#124;string]"/**>.</span></span>