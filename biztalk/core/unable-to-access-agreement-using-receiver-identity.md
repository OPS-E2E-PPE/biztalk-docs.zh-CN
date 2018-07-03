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
ms.openlocfilehash: 630ce4850c2bb11f9b5a18db03204ef2c1e24cae
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003726"
---
# <a name="unable-to-access-agreement-using-receiver-identity"></a><span data-ttu-id="25edc-102">无法使用接收方身份访问协议</span><span class="sxs-lookup"><span data-stu-id="25edc-102">Unable to access agreement using receiver identity</span></span>
## <a name="details"></a><span data-ttu-id="25edc-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="25edc-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="25edc-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="25edc-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="25edc-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="25edc-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="25edc-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="25edc-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="25edc-107">事件源</span><span class="sxs-lookup"><span data-stu-id="25edc-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="25edc-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="25edc-108"> EDI</span></span> |
|    <span data-ttu-id="25edc-109">组件</span><span class="sxs-lookup"><span data-stu-id="25edc-109">Component</span></span>    |                                       <span data-ttu-id="25edc-110">AS2 引擎</span><span class="sxs-lookup"><span data-stu-id="25edc-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="25edc-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="25edc-111">Symbolic Name</span></span>  |                         <span data-ttu-id="25edc-112">UnableToLocateAS2PartyByPartyNameError</span><span class="sxs-lookup"><span data-stu-id="25edc-112">UnableToLocateAS2PartyByPartyNameError</span></span>                         |
|  <span data-ttu-id="25edc-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="25edc-113">Message Text</span></span>   |                <span data-ttu-id="25edc-114">无法使用接收方身份访问协议： {0}</span><span class="sxs-lookup"><span data-stu-id="25edc-114">Unable to access agreement using receiver identity: {0}</span></span>                 |
  
## <a name="explanation"></a><span data-ttu-id="25edc-115">解释</span><span class="sxs-lookup"><span data-stu-id="25edc-115">Explanation</span></span>  
 <span data-ttu-id="25edc-116">此错误表明发送管道无法确定传出的 AS2 消息的参与方，因为它无法匹配传出消息的 AS2To 上下文属性或 Http.UserHttpHeaders 上下文属性中的 AS2To 属性和“AS2 属性”对话框的“作为 AS2 消息接收方的参与方”页中的 AS2-To 属性中参与方的名称。</span><span class="sxs-lookup"><span data-stu-id="25edc-116">This error indicates that the send pipeline could not determine the party for an outgoing AS2 message because it could not match the AS2To context property of the outbound message or the AS2To property in the Http.UserHttpHeaders context property with the name of the party in the AS2-To property in the Party as AS2 Message Receiver page of the AS2 Properties dialog box.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="25edc-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="25edc-117">User Action</span></span>  
 <span data-ttu-id="25edc-118">若要解决此错误，请将“AS2 属性”对话框的“作为 AS2 消息接收方的参与方”页中的 AS2-To 属性设置为与出错的 AS2 消息关联的相应参与方名称。</span><span class="sxs-lookup"><span data-stu-id="25edc-118">To resolve this error, set the AS2-To property in the Party as AS2 Message Receiver page of the AS2 Properties dialog box to the appropriate party name associated with the AS2 message that is in error.</span></span>