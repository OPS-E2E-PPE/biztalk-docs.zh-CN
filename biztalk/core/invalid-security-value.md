---
title: 安全值无效 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ee380da7-c05e-4b9b-84ee-f7ffee90eb0e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ded2a080511992f5e85cda91b39dced703f452f5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381212"
---
# <a name="invalid-security-value"></a><span data-ttu-id="bde43-102">安全值无效</span><span class="sxs-lookup"><span data-stu-id="bde43-102">Invalid Security Value</span></span>
## <a name="details"></a><span data-ttu-id="bde43-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="bde43-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="bde43-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="bde43-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="bde43-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="bde43-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="bde43-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="bde43-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="bde43-107">事件源</span><span class="sxs-lookup"><span data-stu-id="bde43-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="bde43-108">EDI</span><span class="sxs-lookup"><span data-stu-id="bde43-108">EDI</span></span> |
|    <span data-ttu-id="bde43-109">组件</span><span class="sxs-lookup"><span data-stu-id="bde43-109">Component</span></span>    |                                       <span data-ttu-id="bde43-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="bde43-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="bde43-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="bde43-111">Symbolic Name</span></span>  |                         <span data-ttu-id="bde43-112">X12Ta1InvalidSecurityValueDescription</span><span class="sxs-lookup"><span data-stu-id="bde43-112">X12Ta1InvalidSecurityValueDescription</span></span>                          |
|  <span data-ttu-id="bde43-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="bde43-113">Message Text</span></span>   |                                 <span data-ttu-id="bde43-114">安全值无效</span><span class="sxs-lookup"><span data-stu-id="bde43-114">Invalid Security Value</span></span>                                 |
  
## <a name="explanation"></a><span data-ttu-id="bde43-115">解释</span><span class="sxs-lookup"><span data-stu-id="bde43-115">Explanation</span></span>  
 <span data-ttu-id="bde43-116">此错误/警告/信息事件表明接收管道不无法处理传入的交换，因为 ISA04 字段中的安全信息或 UNB6.1 字段中的收件人引用密码值不符合的数据类型和建立服务架构 （X12ServiceSchema 或 EdifactServiceSchema 在 BaseArtifacts.dll 中） 的数字个数。</span><span class="sxs-lookup"><span data-stu-id="bde43-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the Security Information in the ISA04 field or the Recipient Reference Password Value in the UNB6.1 field did not conform to the data type and number of digits established by the service schema (X12ServiceSchema or the EdifactServiceSchema in BaseArtifacts.dll).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bde43-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="bde43-117">User Action</span></span>  
 <span data-ttu-id="bde43-118">若要解决此错误，请确保 ISA04 字段为 X12_AN 数据类型且为 10 个字符 （带或不带尾部空格） 或者 UNB6.1 字段为 EDIFACT_AN 数据类型的并且是介于 1 到 14 个字符之间。</span><span class="sxs-lookup"><span data-stu-id="bde43-118">To resolve this error, make sure that the ISA04 field is of the X12_AN data type and is 10 characters long (with or without trailing spaces) or that the UNB6.1 field is of the EDIFACT_AN data type and is between 1 and 14 characters long.</span></span> <span data-ttu-id="bde43-119">然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="bde43-119">Have the interchange resent.</span></span>