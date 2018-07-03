---
title: 安全限定符无效 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dce36f4b-ab59-41c0-8b92-3020f6393db9
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b8b0bd8b96d493641f58e445c4b45bd9f5df63e2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986934"
---
# <a name="invalid-security-qualifier"></a><span data-ttu-id="19eba-102">安全限定符无效</span><span class="sxs-lookup"><span data-stu-id="19eba-102">Invalid Security Qualifier</span></span>
## <a name="details"></a><span data-ttu-id="19eba-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="19eba-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="19eba-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="19eba-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="19eba-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="19eba-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="19eba-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="19eba-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="19eba-107">事件源</span><span class="sxs-lookup"><span data-stu-id="19eba-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="19eba-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="19eba-108"> EDI</span></span> |
|    <span data-ttu-id="19eba-109">组件</span><span class="sxs-lookup"><span data-stu-id="19eba-109">Component</span></span>    |                                       <span data-ttu-id="19eba-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="19eba-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="19eba-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="19eba-111">Symbolic Name</span></span>  |                       <span data-ttu-id="19eba-112">X12Ta1InvalidSecurityQualifierDescription</span><span class="sxs-lookup"><span data-stu-id="19eba-112">X12Ta1InvalidSecurityQualifierDescription</span></span>                        |
|  <span data-ttu-id="19eba-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="19eba-113">Message Text</span></span>   |                               <span data-ttu-id="19eba-114">安全限定符无效</span><span class="sxs-lookup"><span data-stu-id="19eba-114">Invalid Security Qualifier</span></span>                               |
  
## <a name="explanation"></a><span data-ttu-id="19eba-115">解释</span><span class="sxs-lookup"><span data-stu-id="19eba-115">Explanation</span></span>  
 <span data-ttu-id="19eba-116">此错误/警告/信息事件表明接收管道无法处理传入的交换，因为 ISA03 字段中的安全限定符或 UNB6.2 字段中的收件人引用密码限定符与服务架构（BaseArtifacts.dll 中的 X12ServiceSchema 或 EdifactServiceSchema）建立的枚举中的值不匹配。</span><span class="sxs-lookup"><span data-stu-id="19eba-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the Security Qualifier in the ISA03 field or the Recipient Reference Password Qualifier in the UNB6.2 field did not match a value in the enumeration established by the service schema (X12ServiceSchema or the EdifactServiceSchema in BaseArtifacts.dll).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="19eba-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="19eba-117">User Action</span></span>  
 <span data-ttu-id="19eba-118">若要解决此错误，请确保 ISA03 字段或 UNB6.2 字段与服务架构建立的枚举中的其中一个值匹配。</span><span class="sxs-lookup"><span data-stu-id="19eba-118">To resolve this error, make sure that the ISA03 field or the UNB6.2 field matches one of the values in the enumeration established by the service schema.</span></span> <span data-ttu-id="19eba-119">然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="19eba-119">Have the interchange resent.</span></span>