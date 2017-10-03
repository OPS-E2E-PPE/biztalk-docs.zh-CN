---
title: "架构不包含根元素 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: efc33f2b-9e14-4d2e-8c8a-32b7696f80ea
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c485ce27fc3a1932d7de47557080712e46b654e0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="the-schema-does-not-contain-the-root-element"></a><span data-ttu-id="d1ef1-102">架构不包含根元素</span><span class="sxs-lookup"><span data-stu-id="d1ef1-102">The schema does not contain the root element</span></span>
## <a name="details"></a><span data-ttu-id="d1ef1-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="d1ef1-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d1ef1-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="d1ef1-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="d1ef1-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="d1ef1-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="d1ef1-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="d1ef1-106">Event ID</span></span>|-|  
|<span data-ttu-id="d1ef1-107">事件源</span><span class="sxs-lookup"><span data-stu-id="d1ef1-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="d1ef1-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="d1ef1-108"> EDI</span></span>|  
|<span data-ttu-id="d1ef1-109">组件</span><span class="sxs-lookup"><span data-stu-id="d1ef1-109">Component</span></span>|<span data-ttu-id="d1ef1-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="d1ef1-110">EDI Engine</span></span>|  
|<span data-ttu-id="d1ef1-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="d1ef1-111">Symbolic Name</span></span>|<span data-ttu-id="d1ef1-112">SchemaCode102ENullRootElement</span><span class="sxs-lookup"><span data-stu-id="d1ef1-112">SchemaCode102ENullRootElement</span></span>|  
|<span data-ttu-id="d1ef1-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="d1ef1-113">Message Text</span></span>|<span data-ttu-id="d1ef1-114">架构不包含根元素 {0}</span><span class="sxs-lookup"><span data-stu-id="d1ef1-114">The schema does not contain the root element {0}</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d1ef1-115">解释</span><span class="sxs-lookup"><span data-stu-id="d1ef1-115">Explanation</span></span>  
 <span data-ttu-id="d1ef1-116">接收管道无法处理传入的消息或发送管道无法处理传出消息，因为用来验证消息的架构不包含根元素，该值指示此错误/警告/信息事件。</span><span class="sxs-lookup"><span data-stu-id="d1ef1-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming message or the send pipeline could not process the outgoing message because the schema used to validate the message did not contain the root element.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d1ef1-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="d1ef1-117">User Action</span></span>  
 <span data-ttu-id="d1ef1-118">若要解决此错误，取消部署的文档架构，将根元素添加到架构，然后重新部署架构。</span><span class="sxs-lookup"><span data-stu-id="d1ef1-118">To resolve this error, undeploy the document schema, add the root element to the schema, and then redeploy the schema.</span></span>