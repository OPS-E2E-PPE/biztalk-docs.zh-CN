---
title: 此 AS2 交换的参与方必须包含值为 AS2-从 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5d338759-5646-4dc2-8319-a42aaa8c3d9c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bc5de3b9791c8561f1a2f9e04b2f4915e39454a8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394091"
---
# <a name="the-party-for-this-as2-interchange-must-contain-a-value-for-as2-from"></a><span data-ttu-id="8a04a-102">此 AS2 交换的参与方必须包含值为 AS2-从</span><span class="sxs-lookup"><span data-stu-id="8a04a-102">The party for this AS2 interchange must contain a value for AS2-From</span></span>
## <a name="details"></a><span data-ttu-id="8a04a-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="8a04a-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="8a04a-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="8a04a-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="8a04a-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="8a04a-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="8a04a-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="8a04a-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="8a04a-107">事件源</span><span class="sxs-lookup"><span data-stu-id="8a04a-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="8a04a-108">EDI</span><span class="sxs-lookup"><span data-stu-id="8a04a-108">EDI</span></span> |
|    <span data-ttu-id="8a04a-109">组件</span><span class="sxs-lookup"><span data-stu-id="8a04a-109">Component</span></span>    |                                       <span data-ttu-id="8a04a-110">AS2 引擎</span><span class="sxs-lookup"><span data-stu-id="8a04a-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="8a04a-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="8a04a-111">Symbolic Name</span></span>  |                              <span data-ttu-id="8a04a-112">InvalidAgreementAS2FromName</span><span class="sxs-lookup"><span data-stu-id="8a04a-112">InvalidAgreementAS2FromName</span></span>                               |
|  <span data-ttu-id="8a04a-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="8a04a-113">Message Text</span></span>   |         <span data-ttu-id="8a04a-114">此 AS2 交换的参与方必须包含 AS2-From 的值。</span><span class="sxs-lookup"><span data-stu-id="8a04a-114">The party for this AS2 interchange must contain a value for AS2-From.</span></span>          |
  
## <a name="explanation"></a><span data-ttu-id="8a04a-115">解释</span><span class="sxs-lookup"><span data-stu-id="8a04a-115">Explanation</span></span>  
 <span data-ttu-id="8a04a-116">此错误/警告/信息事件表明发送管道无法发送 AS2 消息，因为没有为解析后的作为消息接收方的参与方设置 AS2-From 属性。</span><span class="sxs-lookup"><span data-stu-id="8a04a-116">This Error/Warning/Information event indicates that the send pipeline could not send the AS2 message because the AS2-From property was not set for the resolved party as message receiver.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8a04a-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="8a04a-117">User Action</span></span>  
 <span data-ttu-id="8a04a-118">若要解决此错误，请打开 BizTalk Server 管理控制台，移动到“参与方”节点，打开为消息解析的参与方的“AS2 属性”对话框，单击“作为 AS2 消息接收方的参与方”节点，然后为“AS2-From”属性输入值。</span><span class="sxs-lookup"><span data-stu-id="8a04a-118">To resolve this error, open the BizTalk Server Administration Console, move to the Parties node, open the AS2 Properties dialog box for the party resolved for the message, click the Party as AS2 Message Receiver node, and then enter a value for the AS2-From property.</span></span>