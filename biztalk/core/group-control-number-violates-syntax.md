---
title: 组控制编号违反语法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e173c914-cb5c-4369-ac2f-8f9abee420cb
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7664a85d0cb1bb0c83ef53c6c584c51b532d6c4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65344874"
---
# <a name="group-control-number-violates-syntax"></a><span data-ttu-id="dbf7a-102">组控制编号违反语法</span><span class="sxs-lookup"><span data-stu-id="dbf7a-102">Group control number violates syntax</span></span>
## <a name="details"></a><span data-ttu-id="dbf7a-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="dbf7a-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="dbf7a-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="dbf7a-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="dbf7a-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="dbf7a-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="dbf7a-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="dbf7a-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="dbf7a-107">事件源</span><span class="sxs-lookup"><span data-stu-id="dbf7a-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="dbf7a-108">EDI</span><span class="sxs-lookup"><span data-stu-id="dbf7a-108">EDI</span></span> |
|    <span data-ttu-id="dbf7a-109">组件</span><span class="sxs-lookup"><span data-stu-id="dbf7a-109">Component</span></span>    |                                       <span data-ttu-id="dbf7a-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="dbf7a-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="dbf7a-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="dbf7a-111">Symbolic Name</span></span>  |                          <span data-ttu-id="dbf7a-112">X12FaInvalidControlNumberDescription</span><span class="sxs-lookup"><span data-stu-id="dbf7a-112">X12FaInvalidControlNumberDescription</span></span>                          |
|  <span data-ttu-id="dbf7a-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="dbf7a-113">Message Text</span></span>   |                          <span data-ttu-id="dbf7a-114">组控制编号违反语法</span><span class="sxs-lookup"><span data-stu-id="dbf7a-114">Group control number violates syntax</span></span>                          |
  
## <a name="explanation"></a><span data-ttu-id="dbf7a-115">解释</span><span class="sxs-lookup"><span data-stu-id="dbf7a-115">Explanation</span></span>  
 <span data-ttu-id="dbf7a-116">此错误/警告/信息事件表明接收管道无法处理传入的 X12 交换的组控制编号的 GS06 和 GE02 字段中的交换，因为不符合的数据类型或中指定的长度服务架构。</span><span class="sxs-lookup"><span data-stu-id="dbf7a-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming X12 interchange because the group control number in the GS06 and GE02 fields of the interchange did not conform to the data type or length specified in the service schema.</span></span> <span data-ttu-id="dbf7a-117">服务架构是 baseartifacts.dll 中的 X12ServiceSchema。</span><span class="sxs-lookup"><span data-stu-id="dbf7a-117">The service schema is the X12ServiceSchema in BaseArtifacts.dll.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="dbf7a-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="dbf7a-118">User Action</span></span>  
 <span data-ttu-id="dbf7a-119">若要解决此错误，请确保交换的 GS06 和 GE02 字段中包含的组控制编号符合的数据类型 (X12_N0) 和服务架构中指定的长度 （介于 1 和 9 位数字） 之间，然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="dbf7a-119">To resolve this error, make sure that the group control numbers contained in the GS06 and GE02 fields of the interchange conform to the data type (X12_N0) and length (between one and nine digits) specified in the service schema, and then have the interchange resent.</span></span>