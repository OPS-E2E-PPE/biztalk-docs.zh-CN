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
ms.openlocfilehash: 5b4db0fe98bcb04f662e4a827f4139e0cff81275
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65331043"
---
# <a name="invalid-as2-from-name-configured-for-party"></a><span data-ttu-id="d41c1-102">无效的 AS2-从配置为参与方名称</span><span class="sxs-lookup"><span data-stu-id="d41c1-102">Invalid AS2-From name configured for Party</span></span>
## <a name="details"></a><span data-ttu-id="d41c1-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="d41c1-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="d41c1-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="d41c1-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="d41c1-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="d41c1-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="d41c1-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="d41c1-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="d41c1-107">事件源</span><span class="sxs-lookup"><span data-stu-id="d41c1-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="d41c1-108">EDI</span><span class="sxs-lookup"><span data-stu-id="d41c1-108">EDI</span></span> |
|    <span data-ttu-id="d41c1-109">组件</span><span class="sxs-lookup"><span data-stu-id="d41c1-109">Component</span></span>    |                                       <span data-ttu-id="d41c1-110">AS2 引擎</span><span class="sxs-lookup"><span data-stu-id="d41c1-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="d41c1-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="d41c1-111">Symbolic Name</span></span>  |                           <span data-ttu-id="d41c1-112">InvalidAS2FromNameConfiguredError</span><span class="sxs-lookup"><span data-stu-id="d41c1-112">InvalidAS2FromNameConfiguredError</span></span>                            |
|  <span data-ttu-id="d41c1-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="d41c1-113">Message Text</span></span>   |              <span data-ttu-id="d41c1-114">无效的 AS2-从为参与方配置的名称：{0}   值： {1}</span><span class="sxs-lookup"><span data-stu-id="d41c1-114">Invalid AS2-From name configured for Party: {0}   Value: {1}</span></span>              |
  
## <a name="explanation"></a><span data-ttu-id="d41c1-115">解释</span><span class="sxs-lookup"><span data-stu-id="d41c1-115">Explanation</span></span>  
 <span data-ttu-id="d41c1-116">此错误/警告/信息事件表明 AS2 编码器或解码器无法处理 AS2 消息因为 as2-From 标头配置为标识的参与方不符合 AS2 RFC 4130 中的规范。</span><span class="sxs-lookup"><span data-stu-id="d41c1-116">This Error/Warning/Information event indicates that the AS2 encoder or decoder could not process the AS2 message because the value of the AS2-From header configured for the identified party did not conform to the specifications in AS2 RFC 4130.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d41c1-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="d41c1-117">User Action</span></span>  
 <span data-ttu-id="d41c1-118">若要解决此错误，请确保 AS2-From 标头配置为参与方符合 AS2 RFC 4130 第，6.2 节中的规范，然后重新发送消息。</span><span class="sxs-lookup"><span data-stu-id="d41c1-118">To resolve this error, make sure that the AS2-From header configured for the party conforms to the specifications in section 6.2 of AS2 RFC 4130, and then have the message resent.</span></span>