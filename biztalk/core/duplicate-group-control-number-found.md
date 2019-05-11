---
title: 找到的组控制编号重复 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1badc033-42fd-4992-ad36-b53047ba7817
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2bfe0fc01b1ff418e0c106c47a303f3608ec5a37
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389495"
---
# <a name="duplicate-group-control-number-found"></a><span data-ttu-id="ca418-102">找到重复组控制编号</span><span class="sxs-lookup"><span data-stu-id="ca418-102">Duplicate group control number found</span></span>
## <a name="details"></a><span data-ttu-id="ca418-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="ca418-103">Details</span></span>  

|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="ca418-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="ca418-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="ca418-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="ca418-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="ca418-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="ca418-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="ca418-107">事件源</span><span class="sxs-lookup"><span data-stu-id="ca418-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="ca418-108">EDI</span><span class="sxs-lookup"><span data-stu-id="ca418-108">EDI</span></span> |
|    <span data-ttu-id="ca418-109">组件</span><span class="sxs-lookup"><span data-stu-id="ca418-109">Component</span></span>    |                                       <span data-ttu-id="ca418-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="ca418-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="ca418-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="ca418-111">Symbolic Name</span></span>  |                                           -                                            |
|  <span data-ttu-id="ca418-112">消息正文</span><span class="sxs-lookup"><span data-stu-id="ca418-112">Message Text</span></span>   |                          <span data-ttu-id="ca418-113">找到重复组控制编号</span><span class="sxs-lookup"><span data-stu-id="ca418-113">Duplicate group control number found</span></span>                          |

## <a name="explanation"></a><span data-ttu-id="ca418-114">解释</span><span class="sxs-lookup"><span data-stu-id="ca418-114">Explanation</span></span>  
 <span data-ttu-id="ca418-115">此错误/警告/信息事件表明 EDI 接收管道可以不处理传入的交换由于具有相同的交换、 组或事务集控制编号与以前接收的交换。</span><span class="sxs-lookup"><span data-stu-id="ca418-115">This Error/Warning/Information event indicates that the EDI receive pipeline could not process an incoming interchange because it had the same interchange, group, or transaction set control number as a previously received interchange.</span></span> <span data-ttu-id="ca418-116">这将导致失败，只要启用了相应的重复控制编号检查。</span><span class="sxs-lookup"><span data-stu-id="ca418-116">This will result in a failure as long as the appropriate duplicate control number checks are enabled.</span></span>  

## <a name="user-action"></a><span data-ttu-id="ca418-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="ca418-117">User Action</span></span>  
 <span data-ttu-id="ca418-118">若要解决此错误，请执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="ca418-118">To resolve this error, do one of the following:</span></span>  

- <span data-ttu-id="ca418-119">如果启用了相应的重复控制编号检查，请确保交换发送到 BizTalk Server 不具有与之前交换相同的组控制编号。</span><span class="sxs-lookup"><span data-stu-id="ca418-119">Ensure that the interchange sent to BizTalk Server does not have the same group control number as a previous interchange, if the corresponding duplicate control number check is enabled.</span></span>  

- <span data-ttu-id="ca418-120">禁用重复组控制编号检查。</span><span class="sxs-lookup"><span data-stu-id="ca418-120">Disable the duplicate group control number check.</span></span> <span data-ttu-id="ca418-121">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击相应的一方，然后打开 EDIFACT 交换处理属性或 X12 作为交换发送方的参与方的交换处理属性对话框。</span><span class="sxs-lookup"><span data-stu-id="ca418-121">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the appropriate party, and open either the EDIFACT Interchange Processing Properties or the X12 Interchange Processing Properties dialog box for the party as an interchange sender.</span></span> <span data-ttu-id="ca418-122">若要禁用 EDIFACT 交换检查，请清除检查重复的 UNG5 （组控制编号） 交换属性中。</span><span class="sxs-lookup"><span data-stu-id="ca418-122">To disable a check for an EDIFACT interchange, clear the Check for duplicate UNG5 (Group control number) in interchange property.</span></span> <span data-ttu-id="ca418-123">若要禁用检查对于 X12 交换，请清除检查重复的 GS6 （组控制编号） 交换属性中。</span><span class="sxs-lookup"><span data-stu-id="ca418-123">To disable a check for an X12 interchange, clear the Check for duplicate GS6 (Group control number) in interchange property.</span></span>
