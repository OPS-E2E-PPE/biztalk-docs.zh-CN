---
title: 无法序列化消息，因为找不到架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 37897c04-650d-4695-846d-b8ba61365647
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da78a4846570b66e95950c61194151c59bbee366
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65325325"
---
# <a name="message-cannot-be-serialized-as-the-schema-could-not-be-located"></a><span data-ttu-id="b217d-102">无法序列化消息，因为找不到架构</span><span class="sxs-lookup"><span data-stu-id="b217d-102">Message cannot be serialized as the schema could not be located</span></span>
## <a name="details"></a><span data-ttu-id="b217d-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="b217d-103">Details</span></span>  
  
|                 |                                                                                                                                          |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="b217d-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="b217d-104">Product Name</span></span>   |                            [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                            |
| <span data-ttu-id="b217d-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="b217d-105">Product Version</span></span> |                                        [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                        |
|    <span data-ttu-id="b217d-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="b217d-106">Event ID</span></span>     |                                                                    -                                                                     |
|  <span data-ttu-id="b217d-107">事件源</span><span class="sxs-lookup"><span data-stu-id="b217d-107">Event Source</span></span>   |                          [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="b217d-108">EDI</span><span class="sxs-lookup"><span data-stu-id="b217d-108">EDI</span></span>                          |
|    <span data-ttu-id="b217d-109">组件</span><span class="sxs-lookup"><span data-stu-id="b217d-109">Component</span></span>    |                                                                <span data-ttu-id="b217d-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="b217d-110">EDI Engine</span></span>                                                                |
|  <span data-ttu-id="b217d-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="b217d-111">Symbolic Name</span></span>  |                                              <span data-ttu-id="b217d-112">MessageSerializationFailureDueToMissingSchema</span><span class="sxs-lookup"><span data-stu-id="b217d-112">MessageSerializationFailureDueToMissingSchema</span></span>                                               |
|  <span data-ttu-id="b217d-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="b217d-113">Message Text</span></span>   | <span data-ttu-id="b217d-114">消息可以不被序列化为架构{0}找不到。</span><span class="sxs-lookup"><span data-stu-id="b217d-114">Message can not be serialized as the schema {0} could not be located.</span></span> <span data-ttu-id="b217d-115">架构未部署或者部署了多个副本。</span><span class="sxs-lookup"><span data-stu-id="b217d-115">Either the schema is not deployed or multiple copies are deployed.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="b217d-116">解释</span><span class="sxs-lookup"><span data-stu-id="b217d-116">Explanation</span></span>  
 <span data-ttu-id="b217d-117">此错误/警告/信息事件表明发送管道无法序列化传出的交换，因为该管道无法确定用于序列化交换所需的架构。</span><span class="sxs-lookup"><span data-stu-id="b217d-117">This Error/Warning/Information event indicates that the send pipeline could not serialize the outgoing interchange because the pipeline could not determine the schema that it needed to use to serialize the interchange.</span></span> <span data-ttu-id="b217d-118">未部署架构或者部署了架构的多个副本。</span><span class="sxs-lookup"><span data-stu-id="b217d-118">The schema was either not deployed or multiple copies of the schema were deployed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b217d-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="b217d-119">User Action</span></span>  
 <span data-ttu-id="b217d-120">若要解决此错误，请执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="b217d-120">To resolve this error, do one of the following:</span></span>  
  
1.  <span data-ttu-id="b217d-121">如果尚未部署与交换关联的架构，请打开 Visual Studio，将架构添加到 BizTalk 项目，然后生成并部署项目。</span><span class="sxs-lookup"><span data-stu-id="b217d-121">If the schema associated with the interchange has not been deployed, open Visual Studio, add the schema to a BizTalk project, and then build and deploy the project.</span></span>  
  
2.  <span data-ttu-id="b217d-122">如果已部署架构的多个副本，请打开 Visual Studio，除了保留一个与交换关联的架构的副本之外，取消部署所有其他副本。</span><span class="sxs-lookup"><span data-stu-id="b217d-122">If more than one copy of the schema has been deployed, open Visual Studio, and undeploy all but one of the copies of the schema associated with the interchange.</span></span>