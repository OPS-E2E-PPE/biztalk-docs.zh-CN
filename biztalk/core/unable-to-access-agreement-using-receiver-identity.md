---
title: 无法使用接收方身份访问协议 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 470325f4-abc4-40bb-9109-9ffc73b496df
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fbdd869e244f3d59ebd267d492112a1e29441c2b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65258498"
---
# <a name="unable-to-access-agreement-using-receiver-identity"></a><span data-ttu-id="af1d8-102">无法使用接收方身份访问协议</span><span class="sxs-lookup"><span data-stu-id="af1d8-102">Unable to access agreement using receiver identity</span></span>
## <a name="details"></a><span data-ttu-id="af1d8-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="af1d8-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="af1d8-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="af1d8-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="af1d8-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="af1d8-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="af1d8-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="af1d8-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="af1d8-107">事件源</span><span class="sxs-lookup"><span data-stu-id="af1d8-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="af1d8-108">EDI</span><span class="sxs-lookup"><span data-stu-id="af1d8-108">EDI</span></span> |
|    <span data-ttu-id="af1d8-109">组件</span><span class="sxs-lookup"><span data-stu-id="af1d8-109">Component</span></span>    |                                       <span data-ttu-id="af1d8-110">AS2 引擎</span><span class="sxs-lookup"><span data-stu-id="af1d8-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="af1d8-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="af1d8-111">Symbolic Name</span></span>  |                         <span data-ttu-id="af1d8-112">UnableToLocateAS2PartyByPartyNameError</span><span class="sxs-lookup"><span data-stu-id="af1d8-112">UnableToLocateAS2PartyByPartyNameError</span></span>                         |
|  <span data-ttu-id="af1d8-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="af1d8-113">Message Text</span></span>   |                <span data-ttu-id="af1d8-114">无法使用接收方身份访问协议： {0}</span><span class="sxs-lookup"><span data-stu-id="af1d8-114">Unable to access agreement using receiver identity: {0}</span></span>                 |
  
## <a name="explanation"></a><span data-ttu-id="af1d8-115">解释</span><span class="sxs-lookup"><span data-stu-id="af1d8-115">Explanation</span></span>  
 <span data-ttu-id="af1d8-116">此错误表明发送管道无法因为它无法匹配的出站消息的 AS2To 上下文属性或 Http.UserHttpHeaders 上下文属性的名称中的 AS2To 属性确定传出的 AS2 消息的参与方在 AS2 参与方的中作为 AS2 消息接收方的 AS2 属性对话框的页的参与方属性。</span><span class="sxs-lookup"><span data-stu-id="af1d8-116">This error indicates that the send pipeline could not determine the party for an outgoing AS2 message because it could not match the AS2To context property of the outbound message or the AS2To property in the Http.UserHttpHeaders context property with the name of the party in the AS2-To property in the Party as AS2 Message Receiver page of the AS2 Properties dialog box.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="af1d8-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="af1d8-117">User Action</span></span>  
 <span data-ttu-id="af1d8-118">若要解决此错误，将 AS2-到中作为 AS2 消息接收方到相应的参与方名称与处于错误的 AS2 消息相关联的 AS2 属性对话框页的参与方属性。</span><span class="sxs-lookup"><span data-stu-id="af1d8-118">To resolve this error, set the AS2-To property in the Party as AS2 Message Receiver page of the AS2 Properties dialog box to the appropriate party name associated with the AS2 message that is in error.</span></span>