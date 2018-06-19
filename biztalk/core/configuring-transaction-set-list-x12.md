---
title: 配置事务集列表 (X12) |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1f277318-90e9-4ad3-843a-e6128837fa2b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18b11ea09c7c3156aea18b95d758228e55994901
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233437"
---
# <a name="configuring-transaction-set-list-x12"></a><span data-ttu-id="3c100-102">配置事务集列表 (X 12)</span><span class="sxs-lookup"><span data-stu-id="3c100-102">Configuring Transaction Set List (X12)</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="3c100-103"> 使您可以定义在处理 EDI 交换时必须始终包括或排除的事务集列表。</span><span class="sxs-lookup"><span data-stu-id="3c100-103"> enables you to define a list of transaction sets that must always be included or excluded while processing an EDI interchange.</span></span> <span data-ttu-id="3c100-104">本部分提供了有关如何创建事务集列表的说明。</span><span class="sxs-lookup"><span data-stu-id="3c100-104">This section provides instructions on how to create the transaction set list.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3c100-105">此处所述的设置同样适用于 HIPAA 交换。</span><span class="sxs-lookup"><span data-stu-id="3c100-105">The settings described here also apply to HIPAA interchanges.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3c100-106">没有属性禁用此页上，即使你清除**本地 BizTalk 处理接收方或支持从该参与方发送消息的消息**时正在创建你为其创建参与方的复选框协议。</span><span class="sxs-lookup"><span data-stu-id="3c100-106">No properties are disabled on this page even if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="3c100-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="3c100-107">Prerequisites</span></span>  
 <span data-ttu-id="3c100-108">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="3c100-108">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-a-transaction-set-list"></a><span data-ttu-id="3c100-109">配置事务集列表</span><span class="sxs-lookup"><span data-stu-id="3c100-109">To configure a transaction set list</span></span>  
  
1.  <span data-ttu-id="3c100-110">创建 X12 编码协议中所述[配置常规设置 (X12)](../core/configuring-general-settings-x12.md)。</span><span class="sxs-lookup"><span data-stu-id="3c100-110">Create an X12 encoding agreement as described in [Configuring General Settings (X12)](../core/configuring-general-settings-x12.md).</span></span> <span data-ttu-id="3c100-111">若要更新现有协议，右键单击在协议**方和业务配置文件**页，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="3c100-111">To update an existing agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="3c100-112">单向协议选项卡上，在**事务设置设置**部分中，单击**事务集列表**。</span><span class="sxs-lookup"><span data-stu-id="3c100-112">On a one-way agreement tab, under **Transaction Set Settings** section, click **Transaction Set List**.</span></span>  
  
3.  <span data-ttu-id="3c100-113">选择**支持事务集，从列表**选项如果你想要创建的必须始终最先处理的事务集的列表。</span><span class="sxs-lookup"><span data-stu-id="3c100-113">Select **Support Transaction Sets from the List** option if you want to create a list of transaction sets that must always be processed.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3c100-114">如果您通常收到具有特定事务类型（例如 850）的交换，则可以使用此选项。</span><span class="sxs-lookup"><span data-stu-id="3c100-114">You would use this option if you typically receive interchanges with specific transaction types, say 850.</span></span> <span data-ttu-id="3c100-115">在这种情况下，可以将该事务类型添加到列表中，以便不会处理其他类型的事务集。</span><span class="sxs-lookup"><span data-stu-id="3c100-115">In that case, you add that transaction type to the list so that the transaction sets of other types are not processed at all.</span></span>  
  
4.  <span data-ttu-id="3c100-116">选择**从列表中排除事务集**选项如果你想要创建的不会处理的事务集的列表。</span><span class="sxs-lookup"><span data-stu-id="3c100-116">Select **Exclude Transaction Sets from the List** option if you want to create a list of transaction sets that must not be processed.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3c100-117">如果您通常接收事务类型变化的交换，则可以使用此选项。</span><span class="sxs-lookup"><span data-stu-id="3c100-117">You would use this option if you typically receive interchanges with varied transaction types.</span></span> <span data-ttu-id="3c100-118">在这种情况下，您需要将这些事务类型添加到不获取任何事务集的列表。</span><span class="sxs-lookup"><span data-stu-id="3c100-118">In that case, you add those transaction type to the list for which you do not get any transaction sets.</span></span>  
  
5.  <span data-ttu-id="3c100-119">单击中的空单元格**ST01**列并从下拉列表中选择事务设置你想要排除上支持的类型。</span><span class="sxs-lookup"><span data-stu-id="3c100-119">Click the empty cell in the **ST01** column and from the drop-down select the transaction set type you want to support on exclude.</span></span>  
  
6.  <span data-ttu-id="3c100-120">若要从列表中删除事务类型，选择事务类型的行，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="3c100-120">To delete a transaction type from the list, select the row for the transaction type, and click **Delete**.</span></span>  
  
7.  <span data-ttu-id="3c100-121">单击**应用**接受所做的更改，然后才能继续进行配置，或单击**确定**验证所做的更改，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="3c100-121">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c100-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3c100-122">See Also</span></span>  
 [<span data-ttu-id="3c100-123">配置事务集设置 (X12)</span><span class="sxs-lookup"><span data-stu-id="3c100-123">Configuring Transaction Set Settings (X12)</span></span>](../core/configuring-transaction-set-settings-x12.md)