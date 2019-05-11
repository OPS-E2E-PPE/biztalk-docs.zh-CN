---
title: 控制编号重复 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 331ad173-29b3-427c-8104-60d80c580a5a
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a3f4e58a6a26390b10d5cc3b4956c1b2fd0864c1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350764"
---
# <a name="duplicate-control-number"></a><span data-ttu-id="d11ec-102">重复控制编号</span><span class="sxs-lookup"><span data-stu-id="d11ec-102">Duplicate Control Number</span></span>
## <a name="details"></a><span data-ttu-id="d11ec-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="d11ec-103">Details</span></span>  

|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="d11ec-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="d11ec-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="d11ec-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="d11ec-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="d11ec-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="d11ec-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="d11ec-107">事件源</span><span class="sxs-lookup"><span data-stu-id="d11ec-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="d11ec-108">EDI</span><span class="sxs-lookup"><span data-stu-id="d11ec-108">EDI</span></span> |
|    <span data-ttu-id="d11ec-109">组件</span><span class="sxs-lookup"><span data-stu-id="d11ec-109">Component</span></span>    |                                       <span data-ttu-id="d11ec-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="d11ec-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="d11ec-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="d11ec-111">Symbolic Name</span></span>  |                                           -                                            |
|  <span data-ttu-id="d11ec-112">消息正文</span><span class="sxs-lookup"><span data-stu-id="d11ec-112">Message Text</span></span>   |                                <span data-ttu-id="d11ec-113">重复控制编号</span><span class="sxs-lookup"><span data-stu-id="d11ec-113">Duplicate Control Number</span></span>                                |

## <a name="explanation"></a><span data-ttu-id="d11ec-114">解释</span><span class="sxs-lookup"><span data-stu-id="d11ec-114">Explanation</span></span>  
 <span data-ttu-id="d11ec-115">此错误/警告/信息事件表明 EDI 接收管道可以不处理传入的交换由于具有相同的交换、 组或事务集控制编号与以前接收的交换。</span><span class="sxs-lookup"><span data-stu-id="d11ec-115">This Error/Warning/Information event indicates that the EDI receive pipeline could not process an incoming interchange because it had the same interchange, group, or transaction set control number as a previously received interchange.</span></span> <span data-ttu-id="d11ec-116">这将导致失败，只要启用了相应的重复控制编号检查。</span><span class="sxs-lookup"><span data-stu-id="d11ec-116">This will result in a failure as long as the appropriate duplicate control number checks are enabled.</span></span>  

## <a name="user-action"></a><span data-ttu-id="d11ec-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="d11ec-117">User Action</span></span>  
 <span data-ttu-id="d11ec-118">若要解决此错误，请执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="d11ec-118">To resolve this error, do one of the following:</span></span>  

- <span data-ttu-id="d11ec-119">请确保的交换发送到 BizTalk Server 不会不具有相同的交换、 组或事务集控制编号与之前交换，如果启用了相应的重复控制编号检查。</span><span class="sxs-lookup"><span data-stu-id="d11ec-119">Ensure that the interchange sent to BizTalk Server does not have the same interchange, group, or transaction set control number as a previous interchange, if the corresponding duplicate control number check is enabled.</span></span>  

- <span data-ttu-id="d11ec-120">禁用重复控制编号检查。</span><span class="sxs-lookup"><span data-stu-id="d11ec-120">Disable the duplicate control number check.</span></span> <span data-ttu-id="d11ec-121">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击相应的一方，然后打开 EDIFACT 交换处理属性或 X12 作为交换发送方的参与方的交换处理属性对话框。</span><span class="sxs-lookup"><span data-stu-id="d11ec-121">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the appropriate party, and open either the EDIFACT Interchange Processing Properties or the X12 Interchange Processing Properties dialog box for the party as an interchange sender.</span></span> <span data-ttu-id="d11ec-122">若要禁用 EDIFACT 交换检查，请清除检查重复的 UNB5 （交换控制编号），检查重复的 ung5 （组控制编号） 中的交换或检查是否有重复的 UNH1 （事务集参考编号） 组属性中。</span><span class="sxs-lookup"><span data-stu-id="d11ec-122">To disable a check for an EDIFACT interchange, clear the Check for duplicate UNB5 (Interchange control number), Check for duplicate UNG5 (Group control number) in interchange, or Check for duplicate UNH1 (Transaction set reference number) in group property.</span></span> <span data-ttu-id="d11ec-123">若要禁用 x12 检查交换，请清除检查重复的 ISA13 （交换控制编号），检查重复的 gs6 （组控制编号） 中的交换或检查是否有重复的 ST2 （事务集控制编号） 组属性中。</span><span class="sxs-lookup"><span data-stu-id="d11ec-123">To disable a check for an X12 interchange, clear the Check for duplicate ISA13 (Interchange control number), Check for duplicate GS6 (Group control number) in interchange, or Check for duplicate ST2 (Transaction set control number) in group property.</span></span>
