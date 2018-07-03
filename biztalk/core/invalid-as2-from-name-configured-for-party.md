---
title: 无效的 AS2-从配置为参与方名称 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cde739bd-f6f7-4e4a-8f02-9a99e9d82fc9
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 136e2e11d20560531bf0f34eb2c93429b6c50f33
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999646"
---
# <a name="invalid-as2-from-name-configured-for-party"></a><span data-ttu-id="8bce8-102">为参与方配置的 AS2-From 名称无效</span><span class="sxs-lookup"><span data-stu-id="8bce8-102">Invalid AS2-From name configured for Party</span></span>
## <a name="details"></a><span data-ttu-id="8bce8-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="8bce8-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="8bce8-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="8bce8-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="8bce8-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="8bce8-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="8bce8-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="8bce8-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="8bce8-107">事件源</span><span class="sxs-lookup"><span data-stu-id="8bce8-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="8bce8-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="8bce8-108"> EDI</span></span> |
|    <span data-ttu-id="8bce8-109">组件</span><span class="sxs-lookup"><span data-stu-id="8bce8-109">Component</span></span>    |                                       <span data-ttu-id="8bce8-110">AS2 引擎</span><span class="sxs-lookup"><span data-stu-id="8bce8-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="8bce8-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="8bce8-111">Symbolic Name</span></span>  |                           <span data-ttu-id="8bce8-112">InvalidAS2FromNameConfiguredError</span><span class="sxs-lookup"><span data-stu-id="8bce8-112">InvalidAS2FromNameConfiguredError</span></span>                            |
|  <span data-ttu-id="8bce8-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="8bce8-113">Message Text</span></span>   |              <span data-ttu-id="8bce8-114">无效的 AS2-从为参与方配置的名称：{0}值： {1}</span><span class="sxs-lookup"><span data-stu-id="8bce8-114">Invalid AS2-From name configured for Party: {0}   Value: {1}</span></span>              |
  
## <a name="explanation"></a><span data-ttu-id="8bce8-115">解释</span><span class="sxs-lookup"><span data-stu-id="8bce8-115">Explanation</span></span>  
 <span data-ttu-id="8bce8-116">此错误/警告/信息事件表明 AS2 编码器或解码器无法处理 AS2 消息，因为为标识的参与方配置的 AS2-From 标头不符合 AS2 RFC 4130 中的规范。</span><span class="sxs-lookup"><span data-stu-id="8bce8-116">This Error/Warning/Information event indicates that the AS2 encoder or decoder could not process the AS2 message because the value of the AS2-From header configured for the identified party did not conform to the specifications in AS2 RFC 4130.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8bce8-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="8bce8-117">User Action</span></span>  
 <span data-ttu-id="8bce8-118">若要解决此错误，请确保为参与方配置的 AS2-From 标头符合 AS2 RFC 4130 第 6.2 节中的规范，然后重新发送消息。</span><span class="sxs-lookup"><span data-stu-id="8bce8-118">To resolve this error, make sure that the AS2-From header configured for the party conforms to the specifications in section 6.2 of AS2 RFC 4130, and then have the message resent.</span></span>