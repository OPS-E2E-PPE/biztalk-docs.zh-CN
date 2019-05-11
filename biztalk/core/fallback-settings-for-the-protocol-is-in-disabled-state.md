---
title: 协议的回退设置处于禁用状态 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f14a5e46-1028-4250-af7b-8137fa927d7e
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bcdf55fba8a8a83f0bf6cc6126707caffe5d0694
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345857"
---
# <a name="fallback-settings-for-the-protocol-is-in-disabled-state"></a><span data-ttu-id="7c704-102">协议的回退设置处于禁用状态</span><span class="sxs-lookup"><span data-stu-id="7c704-102">Fallback Settings for the Protocol is in Disabled state</span></span>
## <a name="details"></a><span data-ttu-id="7c704-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="7c704-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="7c704-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="7c704-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="7c704-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="7c704-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="7c704-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="7c704-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="7c704-107">事件源</span><span class="sxs-lookup"><span data-stu-id="7c704-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="7c704-108">EDI</span><span class="sxs-lookup"><span data-stu-id="7c704-108">EDI</span></span> |
|    <span data-ttu-id="7c704-109">组件</span><span class="sxs-lookup"><span data-stu-id="7c704-109">Component</span></span>    |                                       <span data-ttu-id="7c704-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="7c704-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="7c704-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="7c704-111">Symbolic Name</span></span>  |                      <span data-ttu-id="7c704-112">AgreementResolutionFallbackSettingsDisabled</span><span class="sxs-lookup"><span data-stu-id="7c704-112">AgreementResolutionFallbackSettingsDisabled</span></span>                       |
|  <span data-ttu-id="7c704-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="7c704-113">Message Text</span></span>   |              <span data-ttu-id="7c704-114">后备设置{0}协议处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="7c704-114">Fallback Settings for the {0} Protocol is in Disabled state.</span></span>              |
  
## <a name="explanation"></a><span data-ttu-id="7c704-115">解释</span><span class="sxs-lookup"><span data-stu-id="7c704-115">Explanation</span></span>  
 <span data-ttu-id="7c704-116">此错误/警告/信息事件表明 BizTalk Server 能够解析到某个协议，并且具有已重定向到回退设置和发现的回退设置处于禁用状态的特定协议。</span><span class="sxs-lookup"><span data-stu-id="7c704-116">This Error/Warning/Information event indicates BizTalk Server was able to resolve to an agreement and has been redirected to Fallback settings and found that the fallback settings were in disabled state for the particular protocol.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7c704-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="7c704-117">User Action</span></span>  
 <span data-ttu-id="7c704-118">若要解决此错误，请启用特定协议的回退设置。</span><span class="sxs-lookup"><span data-stu-id="7c704-118">To resolve this error, please enable the fallback settings for the particular protocol.</span></span>