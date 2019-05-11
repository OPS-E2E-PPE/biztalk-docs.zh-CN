---
title: 如何删除 SSO |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Master Secret server, deleting
- SSO, deleting
- deleting, SSO
- deleting, Master Secret server
ms.assetid: 0e1ad8e3-0938-4f36-b85b-4631d0eeb8c9
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5c72d8a0f718ce42adbae6eacde6b5a140d82469
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384260"
---
# <a name="how-to-remove-sso"></a><span data-ttu-id="29da2-102">如何删除 SSO</span><span class="sxs-lookup"><span data-stu-id="29da2-102">How to Remove SSO</span></span>
<span data-ttu-id="29da2-103">如果你删除 BizTalk Server，除非依存产品要使用它不再配置企业单一登录 (SSO)。</span><span class="sxs-lookup"><span data-stu-id="29da2-103">If you remove BizTalk Server, Enterprise Single Sign-On (SSO) is no longer configured unless a dependent product is using it.</span></span> <span data-ttu-id="29da2-104">但是，不将其删除。</span><span class="sxs-lookup"><span data-stu-id="29da2-104">However, it is not removed.</span></span> <span data-ttu-id="29da2-105">必须单独删除 SSO。</span><span class="sxs-lookup"><span data-stu-id="29da2-105">You must remove SSO separately.</span></span> <span data-ttu-id="29da2-106">您还可以还原包括主密钥以重复使用现有数据的配置信息。</span><span class="sxs-lookup"><span data-stu-id="29da2-106">You can also restore configuration information including the master secret to reuse existing data.</span></span> <span data-ttu-id="29da2-107">有关详细信息，请参阅[如何还原主密钥](../core/how-to-restore-the-master-secret.md)。</span><span class="sxs-lookup"><span data-stu-id="29da2-107">For more information, see [How to Restore the Master Secret](../core/how-to-restore-the-master-secret.md).</span></span>  
  
### <a name="to-remove-enterprise-single-sign-on"></a><span data-ttu-id="29da2-108">若要删除企业单一登录</span><span class="sxs-lookup"><span data-stu-id="29da2-108">To remove Enterprise Single Sign-On</span></span>  
  
1. <span data-ttu-id="29da2-109">备份主密钥。</span><span class="sxs-lookup"><span data-stu-id="29da2-109">Back up the master secret key.</span></span> <span data-ttu-id="29da2-110">有关详细信息，请参阅[如何返回主密钥](../core/how-to-back-up-the-master-secret.md)。</span><span class="sxs-lookup"><span data-stu-id="29da2-110">For more information, see [How to Back Up the Master Secret](../core/how-to-back-up-the-master-secret.md).</span></span>  
  
2. <span data-ttu-id="29da2-111">卸载[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="29da2-111">Uninstall [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
3. <span data-ttu-id="29da2-112">在 **“开始”** 菜单上，单击 **“控制面板”**。</span><span class="sxs-lookup"><span data-stu-id="29da2-112">On the **Start** menu, click **Control Panel**.</span></span>  
  
4. <span data-ttu-id="29da2-113">单击**添加/删除程序**。</span><span class="sxs-lookup"><span data-stu-id="29da2-113">Click **Add/Remove Programs**.</span></span>  
  
5. <span data-ttu-id="29da2-114">在中**添加/删除程序**对话框中，单击**Microsoft 企业单一登录**，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="29da2-114">In the **Add/Remove Programs** dialog box, click **Microsoft Enterprise Single Sign-On**, and then click **Remove**.</span></span>  
  
6. <span data-ttu-id="29da2-115">单击**是**当系统提示你确认该删除的 Microsoft 企业单一登录。</span><span class="sxs-lookup"><span data-stu-id="29da2-115">Click **Yes** when prompted to confirm the removal of Microsoft Enterprise Single Sign-On.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="29da2-116">如果你有 BizTalk Server 运行时、 开发或管理功能安装或安装 Host Integration Server 管理功能，您将不能卸载 SSO 运行时或管理组件，直到所有依赖项删除。</span><span class="sxs-lookup"><span data-stu-id="29da2-116">If you have BizTalk Server Runtime, Development, or Administration features installed, or Host Integration Server Administration features installed, you will not be able to uninstall the SSO Runtime or Administration components until all dependencies are removed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29da2-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="29da2-117">See Also</span></span>  
 [<span data-ttu-id="29da2-118">安装 SSO</span><span class="sxs-lookup"><span data-stu-id="29da2-118">Installing SSO</span></span>](../core/installing-sso.md)