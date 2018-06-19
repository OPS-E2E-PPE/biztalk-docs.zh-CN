---
title: 找不到的协议的回退设置 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d93e5db1-16a3-4796-8fa2-fef934508034
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5b3f8ea35f4f29859f5156ff254137ea7a8f8db
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22245901"
---
# <a name="fallback-settings-for-the-protocol-not-found"></a><span data-ttu-id="0d8be-102">找不到协议的后备设置</span><span class="sxs-lookup"><span data-stu-id="0d8be-102">Fallback Settings for the Protocol not found</span></span>
## <a name="details"></a><span data-ttu-id="0d8be-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="0d8be-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0d8be-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="0d8be-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="0d8be-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="0d8be-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="0d8be-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="0d8be-106">Event ID</span></span>|-|  
|<span data-ttu-id="0d8be-107">事件源</span><span class="sxs-lookup"><span data-stu-id="0d8be-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="0d8be-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="0d8be-108"> EDI</span></span>|  
|<span data-ttu-id="0d8be-109">组件</span><span class="sxs-lookup"><span data-stu-id="0d8be-109">Component</span></span>|<span data-ttu-id="0d8be-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="0d8be-110">EDI Engine</span></span>|  
|<span data-ttu-id="0d8be-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="0d8be-111">Symbolic Name</span></span>|<span data-ttu-id="0d8be-112">AgreementResolutionFallbackSettingsNotFound</span><span class="sxs-lookup"><span data-stu-id="0d8be-112">AgreementResolutionFallbackSettingsNotFound</span></span>|  
|<span data-ttu-id="0d8be-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="0d8be-113">Message Text</span></span>|<span data-ttu-id="0d8be-114">找不到 {0} 协议的回退设置。</span><span class="sxs-lookup"><span data-stu-id="0d8be-114">Fallback Settings for the {0} Protocol not found.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0d8be-115">解释</span><span class="sxs-lookup"><span data-stu-id="0d8be-115">Explanation</span></span>  
 <span data-ttu-id="0d8be-116">此错误/警告/信息事件表明 BizTalk Server 能够解析到某个协议且已重定向到回退设置，但发现特定协议没有回退设置。</span><span class="sxs-lookup"><span data-stu-id="0d8be-116">This Error/Warning/Information event indicates BizTalk Server was able to resolve to an agreement and has been redirected to Fallback settings and found that the fallback settings were not there for the particular protocol.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0d8be-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="0d8be-117">User Action</span></span>  
 <span data-ttu-id="0d8be-118">若要解决此错误，请为特定协议配置回退设置。</span><span class="sxs-lookup"><span data-stu-id="0d8be-118">To resolve this error, please configure the fallback settings for the particular protocol.</span></span>