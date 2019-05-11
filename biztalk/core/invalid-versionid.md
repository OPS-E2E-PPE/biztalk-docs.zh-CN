---
title: VersionId 无效 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 563af6e8-f496-46c9-8b5f-7b941b2d08a5
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9cc840ab57b9421aabedcffbd3ae570a2553bd74
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65330029"
---
# <a name="invalid-versionid"></a><span data-ttu-id="d2c58-102">VersionId 无效</span><span class="sxs-lookup"><span data-stu-id="d2c58-102">Invalid VersionId</span></span>
## <a name="details"></a><span data-ttu-id="d2c58-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="d2c58-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="d2c58-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="d2c58-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="d2c58-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="d2c58-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="d2c58-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="d2c58-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="d2c58-107">事件源</span><span class="sxs-lookup"><span data-stu-id="d2c58-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="d2c58-108">EDI</span><span class="sxs-lookup"><span data-stu-id="d2c58-108">EDI</span></span> |
|    <span data-ttu-id="d2c58-109">组件</span><span class="sxs-lookup"><span data-stu-id="d2c58-109">Component</span></span>    |                                       <span data-ttu-id="d2c58-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="d2c58-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="d2c58-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="d2c58-111">Symbolic Name</span></span>  |                           <span data-ttu-id="d2c58-112">X12Ta1InvalidVersionIdDescription</span><span class="sxs-lookup"><span data-stu-id="d2c58-112">X12Ta1InvalidVersionIdDescription</span></span>                            |
|  <span data-ttu-id="d2c58-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="d2c58-113">Message Text</span></span>   |                                   <span data-ttu-id="d2c58-114">VersionId 无效</span><span class="sxs-lookup"><span data-stu-id="d2c58-114">Invalid VersionId</span></span>                                    |
  
## <a name="explanation"></a><span data-ttu-id="d2c58-115">解释</span><span class="sxs-lookup"><span data-stu-id="d2c58-115">Explanation</span></span>  
 <span data-ttu-id="d2c58-116">此错误/警告/信息事件表明接收管道无法处理传入的交换，因为交换中的版本标识符（X12 交换中的 GS08 字段或 EDIFACT 交换中的 UNG7 字段）不符合服务架构（BaseArtifacts.dll 中的 X12ServiceSchema 或 EdifactServiceSchema）建立的数据类型和位数。</span><span class="sxs-lookup"><span data-stu-id="d2c58-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the version identifier in the interchange (the GS08 field in an X12 interchange or the UNG7 field in an EDIFACT interchange) did not conform to the data type and number of digits established by the service schema (X12ServiceSchema or the EdifactServiceSchema in BaseArtifacts.dll).</span></span> <span data-ttu-id="d2c58-117">GS08 字段必须是 X12_AN 数据类型并且必须介于 1 和 12 位之间。</span><span class="sxs-lookup"><span data-stu-id="d2c58-117">The GS08 field must be of the X12_AN data type and between 1 and 12 digits.</span></span> <span data-ttu-id="d2c58-118">UNG7.1 中的版本必须是 EDIFACT_AN 数据类型并且必须介于 1 和 3 位之间。</span><span class="sxs-lookup"><span data-stu-id="d2c58-118">The version in UNG7.1 must be of the EDIFACT_AN data type and between 1 and 3 digits.</span></span> <span data-ttu-id="d2c58-119">UNG7.2 中的版本必须是 EDIFACT_AN 数据类型并且必须介于 1 和 3 位之间。</span><span class="sxs-lookup"><span data-stu-id="d2c58-119">The release in UNG7.2 must be of the EDIFACT_AN data type and between 1 and 3 digits.</span></span> <span data-ttu-id="d2c58-120">UNG7.3 中的协会分配代码必须是 EDIFACT_AN 数据类型并且必须介于 1 和 6 位之间。</span><span class="sxs-lookup"><span data-stu-id="d2c58-120">The Association assigned code in UNG7.3 must be of the EDIFACT_AN data type and between 1 and 6 digits.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d2c58-121">用户操作</span><span class="sxs-lookup"><span data-stu-id="d2c58-121">User Action</span></span>  
 <span data-ttu-id="d2c58-122">若要解决此错误，请确保 GS08 或 UNG7 中的版本符合架构指定的数据类型和位数，然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="d2c58-122">To resolve this error, make sure that the version in GS08 or UNG7 conforms to the data type and number of digits specified by the service schema, and then have the interchange resent.</span></span>