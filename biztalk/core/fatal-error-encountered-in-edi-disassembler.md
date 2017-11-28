---
title: "在 EDI 反汇编程序中遇到错误 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: da562612-c27a-49b6-8334-3b410a6e025e
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1b4e65cd3b330588d3484f13f720d15a722d50f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="fatal-error-encountered-in-edi-disassembler"></a><span data-ttu-id="9c7bd-102">在 EDI 拆装器中遇到严重错误</span><span class="sxs-lookup"><span data-stu-id="9c7bd-102">Fatal error encountered in EDI Disassembler</span></span>
## <a name="details"></a><span data-ttu-id="9c7bd-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="9c7bd-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9c7bd-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="9c7bd-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="9c7bd-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="9c7bd-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="9c7bd-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="9c7bd-106">Event ID</span></span>|-|  
|<span data-ttu-id="9c7bd-107">事件源</span><span class="sxs-lookup"><span data-stu-id="9c7bd-107">Event Source</span></span>|<span data-ttu-id="9c7bd-108">BizTalk Server EDI</span><span class="sxs-lookup"><span data-stu-id="9c7bd-108">BizTalk Server EDI</span></span>|  
|<span data-ttu-id="9c7bd-109">组件</span><span class="sxs-lookup"><span data-stu-id="9c7bd-109">Component</span></span>|<span data-ttu-id="9c7bd-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="9c7bd-110">EDI Engine</span></span>|  
|<span data-ttu-id="9c7bd-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="9c7bd-111">Symbolic Name</span></span>|<span data-ttu-id="9c7bd-112">EdiDasmFatalError</span><span class="sxs-lookup"><span data-stu-id="9c7bd-112">EdiDasmFatalError</span></span>|  
|<span data-ttu-id="9c7bd-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="9c7bd-113">Message Text</span></span>|<span data-ttu-id="9c7bd-114">在 EDI 拆装器中遇到错误，错误信息为 {0}</span><span class="sxs-lookup"><span data-stu-id="9c7bd-114">Fatal error encountered in EDI Disassembler, error information is {0}</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="9c7bd-115">解释</span><span class="sxs-lookup"><span data-stu-id="9c7bd-115">Explanation</span></span>  
 <span data-ttu-id="9c7bd-116">此错误/警告/信息事件表明由于 EDI 拆装器中指明的错误，接收管道无法处理传入的交换。</span><span class="sxs-lookup"><span data-stu-id="9c7bd-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because of the indicated error in the EDI Disassembler.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9c7bd-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="9c7bd-117">User Action</span></span>  
 <span data-ttu-id="9c7bd-118">若要解决此错误，请确定所指明的错误的源，并参阅产品帮助以确定如何解决此错误。</span><span class="sxs-lookup"><span data-stu-id="9c7bd-118">To resolve this error, identify the source of the indicated error, and refer to the product help to determine how to fix it.</span></span>