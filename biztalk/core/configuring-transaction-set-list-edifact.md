---
title: 配置事务集列表 (EDIFACT) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b03ace75-70bf-47c9-9a94-df813d7cab1e
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5768fc6dcf0e5569acb1d07db38fedc301fb566b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390623"
---
# <a name="configuring-transaction-set-list-edifact"></a><span data-ttu-id="af860-102">配置事务集列表 (EDIFACT)</span><span class="sxs-lookup"><span data-stu-id="af860-102">Configuring Transaction Set List (EDIFACT)</span></span>
<span data-ttu-id="af860-103">BizTalk Server，可定义必须始终包含或排除处理 EDI 交换时的事务集的列表。</span><span class="sxs-lookup"><span data-stu-id="af860-103">BizTalk Server enables you to define a list of transaction sets that must always be included or excluded while processing an EDI interchange.</span></span> <span data-ttu-id="af860-104">本部分提供有关如何创建事务集列表。</span><span class="sxs-lookup"><span data-stu-id="af860-104">This section provides instructions on how to create the transaction set list.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="af860-105">没有属性禁用此页上，即使您清除**本地 BizTalk 处理参与方或支持来自此参与方发送消息的接收的消息**要为其创建的参与方时的复选框协议。</span><span class="sxs-lookup"><span data-stu-id="af860-105">No properties are disabled on this page even if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="af860-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="af860-106">Prerequisites</span></span>  
 <span data-ttu-id="af860-107">必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。</span><span class="sxs-lookup"><span data-stu-id="af860-107">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-a-transaction-set-list"></a><span data-ttu-id="af860-108">若要配置事务集列表</span><span class="sxs-lookup"><span data-stu-id="af860-108">To configure a transaction set list</span></span>  
  
1.  <span data-ttu-id="af860-109">创建 EDIFACT 编码协议，如中所述[配置常规设置 (EDIFACT)](../core/configuring-general-settings-edifact.md)。</span><span class="sxs-lookup"><span data-stu-id="af860-109">Create an EDIFACT encoding agreement as described in [Configuring General Settings (EDIFACT)](../core/configuring-general-settings-edifact.md).</span></span> <span data-ttu-id="af860-110">若要更新现有的协议，请右键单击中的协议**参与方和业务配置文件**页，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="af860-110">To update an existing agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="af860-111">在单向协议选项卡下**事务集设置**部分中，单击**事务集列表**。</span><span class="sxs-lookup"><span data-stu-id="af860-111">On a one-way agreement tab, under **Transaction Set Settings** section, click **Transaction Set List**.</span></span>  
  
3.  <span data-ttu-id="af860-112">选择**从列表中支持事务集**选项如果想要创建始终必须处理的事务集的列表。</span><span class="sxs-lookup"><span data-stu-id="af860-112">Select **Support Transaction Sets from the List** option if you want to create a list of transaction sets that must always be processed.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="af860-113">如果您通常收到具有特定事务类型的交换，可以使用此选项假设 APERAK。</span><span class="sxs-lookup"><span data-stu-id="af860-113">You would use this option if you typically receive interchanges with specific transaction types, say APERAK.</span></span> <span data-ttu-id="af860-114">在这种情况下，您添加的事务类型设置为列表，以便其他类型的事务集根本不处理。</span><span class="sxs-lookup"><span data-stu-id="af860-114">In that case, you add that transaction type to the list so that the transaction sets of other types are not processed at all.</span></span>  
  
4.  <span data-ttu-id="af860-115">选择**从列表中排除事务集**选项如果想要创建不得处理的事务集的列表。</span><span class="sxs-lookup"><span data-stu-id="af860-115">Select **Exclude Transaction Sets from the List** option if you want to create a list of transaction sets that must not be processed.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="af860-116">如果您通常接收事务类型变化的交换，可以使用此选项。</span><span class="sxs-lookup"><span data-stu-id="af860-116">You would use this option if you typically receive interchanges with varied transaction types.</span></span> <span data-ttu-id="af860-117">在这种情况下，您还将这些事务类型添加到你无法获得任何事务的列表设置。</span><span class="sxs-lookup"><span data-stu-id="af860-117">In that case, you add those transaction type to the list for which you do not get any transaction sets.</span></span>  
  
5.  <span data-ttu-id="af860-118">单击的空单元格中**UNH2.1**列并从下拉列表中选择事务集你想要支持排除类型。</span><span class="sxs-lookup"><span data-stu-id="af860-118">Click the empty cell in the **UNH2.1** column and from the drop-down select the transaction set type you want to support on exclude.</span></span>  
  
6.  <span data-ttu-id="af860-119">若要从列表中删除事务类型，选择事务类型的行，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="af860-119">To delete a transaction type from the list, select the row for the transaction type, and click **Delete**.</span></span>  
  
7.  <span data-ttu-id="af860-120">单击**Apply**以接受更改，然后才能继续进行配置，或单击**确定**以验证所做的更改，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="af860-120">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af860-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="af860-121">See Also</span></span>  
 [<span data-ttu-id="af860-122">配置事务集设置 (EDIFACT)</span><span class="sxs-lookup"><span data-stu-id="af860-122">Configuring Transaction Set Settings (EDIFACT)</span></span>](../core/configuring-transaction-set-settings-edifact.md)