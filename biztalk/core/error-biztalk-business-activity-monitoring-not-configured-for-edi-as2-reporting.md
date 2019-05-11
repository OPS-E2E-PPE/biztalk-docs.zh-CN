---
title: BizTalk 业务活动监视具有尚未配置 EDI-AS2 状态报告 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2f46c1c8-2771-4b16-8fb1-71952792ac4a
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 58b6326829f6077b52acdca24d87b81acb3bc481
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65349035"
---
# <a name="biztalk-business-activity-monitoring-has-not-been-configured-for-edi-as2-status-reporting"></a><span data-ttu-id="1d8db-102">BizTalk 业务活动监视具有尚未配置 EDI-AS2 状态报告</span><span class="sxs-lookup"><span data-stu-id="1d8db-102">BizTalk Business Activity Monitoring has not been configured for EDI-AS2 status reporting</span></span>
## <a name="details"></a><span data-ttu-id="1d8db-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="1d8db-103">Details</span></span>  
  
|                 |                                                                                                                                             |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="1d8db-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="1d8db-104">Product Name</span></span>   |                             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                              |
| <span data-ttu-id="1d8db-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="1d8db-105">Product Version</span></span> |                                         [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                          |
|    <span data-ttu-id="1d8db-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="1d8db-106">Event ID</span></span>     |                                                                      -                                                                      |
|  <span data-ttu-id="1d8db-107">事件源</span><span class="sxs-lookup"><span data-stu-id="1d8db-107">Event Source</span></span>   |                           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="1d8db-108">EDI</span><span class="sxs-lookup"><span data-stu-id="1d8db-108">EDI</span></span>                            |
|    <span data-ttu-id="1d8db-109">组件</span><span class="sxs-lookup"><span data-stu-id="1d8db-109">Component</span></span>    |                                                                 <span data-ttu-id="1d8db-110">AS2 引擎</span><span class="sxs-lookup"><span data-stu-id="1d8db-110">AS2 Engine</span></span>                                                                  |
|  <span data-ttu-id="1d8db-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="1d8db-111">Symbolic Name</span></span>  |                                                                      -                                                                      |
|  <span data-ttu-id="1d8db-112">消息正文</span><span class="sxs-lookup"><span data-stu-id="1d8db-112">Message Text</span></span>   | <span data-ttu-id="1d8db-113">尚未针对 EDI/AS2 状态报告配置 BizTalk 业务活动监视。</span><span class="sxs-lookup"><span data-stu-id="1d8db-113">BizTalk Business Activity Monitoring has not been configured for EDI/AS2 status reporting.</span></span> <span data-ttu-id="1d8db-114">因此将禁用状态报告功能。</span><span class="sxs-lookup"><span data-stu-id="1d8db-114">Hence status reporting feature will be disabled.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="1d8db-115">解释</span><span class="sxs-lookup"><span data-stu-id="1d8db-115">Explanation</span></span>  
 <span data-ttu-id="1d8db-116">此错误/警告/信息事件表明未启用 EDI/AS2 状态报告，因为尚未通过 BizTalk 配置向导配置业务活动监视 (BAM)。</span><span class="sxs-lookup"><span data-stu-id="1d8db-116">This Error/Warning/Information event indicates that EDI/AS2 status reporting is not enabled because Business Activity Monitoring (BAM) has not been configured through the BizTalk Configuration Wizard.</span></span> <span data-ttu-id="1d8db-117">BAM 基础结构对于 EDI/AS2 状态报告来说是必不可少的。</span><span class="sxs-lookup"><span data-stu-id="1d8db-117">The BAM infrastructure is a prerequisite for EDI/AS2 status reporting.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1d8db-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="1d8db-118">User Action</span></span>  
 <span data-ttu-id="1d8db-119">若要解决此错误，请运行 BizTalk 配置向导并配置业务活动监视。</span><span class="sxs-lookup"><span data-stu-id="1d8db-119">To resolve this error, run the BizTalk Configuration Wizard and configure Business Activity Monitoring.</span></span>