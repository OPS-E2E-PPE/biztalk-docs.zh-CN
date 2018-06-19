---
title: 删除使用规则验证 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- policies, deleting rules
- rules
ms.assetid: b2b0dabf-8f99-4b85-95da-6bbf3e79ad41
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 017184e5f530096dc0ca166fdaaa9810a3372cfa
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25962115"
---
# <a name="removing-usage-rule-validation"></a><span data-ttu-id="92c08-102">删除使用规则验证</span><span class="sxs-lookup"><span data-stu-id="92c08-102">Removing Usage Rule Validation</span></span>
<span data-ttu-id="92c08-103">使用规则 SWIFT 标准中定义并由强制实施[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]特定于每种消息类型的业务策略。</span><span class="sxs-lookup"><span data-stu-id="92c08-103">Usage rules are defined in SWIFT standards and enforced by [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] business policies specific to each message type.</span></span> <span data-ttu-id="92c08-104">这些使用规则是可以使用提供的字段的额外验证的指南。</span><span class="sxs-lookup"><span data-stu-id="92c08-104">These usage rules are guidelines that you can use to provide extra validation for a field.</span></span> <span data-ttu-id="92c08-105">与网络验证规则、 是必需的你可以选择不需要使用规则的消息类型。</span><span class="sxs-lookup"><span data-stu-id="92c08-105">Unlike network validation rules, which are mandatory, you can choose not to require usage rules for a message type.</span></span> <span data-ttu-id="92c08-106">如果是这种情况，你可以执行以下任一操作：</span><span class="sxs-lookup"><span data-stu-id="92c08-106">If that is the case, you can do either of the following:</span></span>  
  
-   <span data-ttu-id="92c08-107">你可以删除特定的业务规则强制执行来自消息类型验证策略的使用情况规则。</span><span class="sxs-lookup"><span data-stu-id="92c08-107">You can remove a specific business rule that enforces a usage rule from the message-type validation policy.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="92c08-108">从策略中删除规则将其永久移除。</span><span class="sxs-lookup"><span data-stu-id="92c08-108">Removing a rule from the policy will remove it permanently.</span></span>  
  
-   <span data-ttu-id="92c08-109">如果你不希望强制执行任何使用规则，你可以取消部署消息类型的验证策略。</span><span class="sxs-lookup"><span data-stu-id="92c08-109">If you do not want to enforce any of the usage rules, you can undeploy the validation policy for a message type.</span></span>  
  
### <a name="to-remove-a-rule-from-a-policy"></a><span data-ttu-id="92c08-110">若要从策略中删除规则</span><span class="sxs-lookup"><span data-stu-id="92c08-110">To remove a rule from a policy</span></span>  
  
1.  <span data-ttu-id="92c08-111">在文本编辑器中，（如记事本） 打开你想要更改，例如，在 MT103_Validation_Policy 验证策略*\<驱动器\>*: files\ Microsoft BizTalk Accelerator for SWIFT \<版本\>消息 Pack\SWIFT Messages\A4SWIFT SRG\<版本\>\Category 1\MT103。</span><span class="sxs-lookup"><span data-stu-id="92c08-111">In a text editor, such as Notepad, open the validation policy that you want to change, for example, MT103_Validation_Policy in *\<drive\>*:\Program Files\ Microsoft BizTalk Accelerator for SWIFT \<version\> Message Pack\SWIFT Messages\A4SWIFT-SRG\<version\>\Category 1\MT103.</span></span>  
  
2.  <span data-ttu-id="92c08-112">删除规则节点，你不想，然后保存策略。</span><span class="sxs-lookup"><span data-stu-id="92c08-112">Remove the rule node that you do not want, and then save the policy.</span></span>  
  
3.  <span data-ttu-id="92c08-113">使用业务规则引擎部署向导进行发布和部署策略。</span><span class="sxs-lookup"><span data-stu-id="92c08-113">Use the Business Rules Engine Deployment Wizard to publish and deploy the policy.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="92c08-114">你可以创建的策略的副本，删除特定的规则，然后将其部署已修改的策略从验证策略中删除规则。</span><span class="sxs-lookup"><span data-stu-id="92c08-114">You can also remove a rule from a validation policy by creating a copy of the policy, removing the specific rule, and then deploying the modified policy.</span></span> <span data-ttu-id="92c08-115">取消部署以前版本的策略。</span><span class="sxs-lookup"><span data-stu-id="92c08-115">Undeploy the previous version of the policy.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="92c08-116">在业务规则编辑器，无法从已发布或部署的策略中删除规则。</span><span class="sxs-lookup"><span data-stu-id="92c08-116">In Business Rule Composer, you cannot delete a rule from a published or deployed policy.</span></span>  
  
### <a name="to-remove-the-policy-for-a-message-type"></a><span data-ttu-id="92c08-117">若要删除的消息类型的策略</span><span class="sxs-lookup"><span data-stu-id="92c08-117">To remove the policy for a message type</span></span>  
  
1.  <span data-ttu-id="92c08-118">单击**启动**，指向**程序**，指向**Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**业务规则编辑器**。</span><span class="sxs-lookup"><span data-stu-id="92c08-118">Click **Start**, point to **Programs**, point to **Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)], and then click **Business Rule Composer**.</span></span>  
  
2.  <span data-ttu-id="92c08-119">在策略资源管理器，找到消息类型，例如，MT103_Validation_Policy 的部署的验证策略。</span><span class="sxs-lookup"><span data-stu-id="92c08-119">In Policy Explorer, find the deployed validation policy for the message type, for example, MT103_Validation_Policy.</span></span>  
  
3.  <span data-ttu-id="92c08-120">右键单击的策略，请单击**取消部署后再次**，单击**删除**，然后单击**是**。</span><span class="sxs-lookup"><span data-stu-id="92c08-120">Right-click the policy, click **Undeploy**, click **Delete**, and then click **Yes**.</span></span>