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
ms.openlocfilehash: fb712972c0fd7ba8975f30ee6519812dd863e442
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004102"
---
# <a name="how-to-remove-sso"></a><span data-ttu-id="2234b-102">如何删除 SSO</span><span class="sxs-lookup"><span data-stu-id="2234b-102">How to Remove SSO</span></span>
<span data-ttu-id="2234b-103">除非依存产品要使用企业单一登录 (SSO)，否则在删除 BizTalk Server 时将不再配置 SSO。</span><span class="sxs-lookup"><span data-stu-id="2234b-103">If you remove BizTalk Server, Enterprise Single Sign-On (SSO) is no longer configured unless a dependent product is using it.</span></span> <span data-ttu-id="2234b-104">不过，这样并未删除 SSO。</span><span class="sxs-lookup"><span data-stu-id="2234b-104">However, it is not removed.</span></span> <span data-ttu-id="2234b-105">您必须单独删除 SSO。</span><span class="sxs-lookup"><span data-stu-id="2234b-105">You must remove SSO separately.</span></span> <span data-ttu-id="2234b-106">也可以还原包括主密钥在内的配置信息以重用现有数据。</span><span class="sxs-lookup"><span data-stu-id="2234b-106">You can also restore configuration information including the master secret to reuse existing data.</span></span> <span data-ttu-id="2234b-107">有关详细信息，请参阅[如何还原主密钥](../core/how-to-restore-the-master-secret.md)。</span><span class="sxs-lookup"><span data-stu-id="2234b-107">For more information, see [How to Restore the Master Secret](../core/how-to-restore-the-master-secret.md).</span></span>  
  
### <a name="to-remove-enterprise-single-sign-on"></a><span data-ttu-id="2234b-108">删除企业单一登录</span><span class="sxs-lookup"><span data-stu-id="2234b-108">To remove Enterprise Single Sign-On</span></span>  
  
1. <span data-ttu-id="2234b-109">备份主密钥。</span><span class="sxs-lookup"><span data-stu-id="2234b-109">Back up the master secret key.</span></span> <span data-ttu-id="2234b-110">有关详细信息，请参阅[如何返回主密钥](../core/how-to-back-up-the-master-secret.md)。</span><span class="sxs-lookup"><span data-stu-id="2234b-110">For more information, see [How to Back Up the Master Secret](../core/how-to-back-up-the-master-secret.md).</span></span>  
  
2. <span data-ttu-id="2234b-111">卸载 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="2234b-111">Uninstall [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
3. <span data-ttu-id="2234b-112">在 **“开始”** 菜单上，单击 **“控制面板”**。</span><span class="sxs-lookup"><span data-stu-id="2234b-112">On the **Start** menu, click **Control Panel**.</span></span>  
  
4. <span data-ttu-id="2234b-113">单击**添加/删除程序**。</span><span class="sxs-lookup"><span data-stu-id="2234b-113">Click **Add/Remove Programs**.</span></span>  
  
5. <span data-ttu-id="2234b-114">在中**添加/删除程序**对话框中，单击**Microsoft 企业单一登录**，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="2234b-114">In the **Add/Remove Programs** dialog box, click **Microsoft Enterprise Single Sign-On**, and then click **Remove**.</span></span>  
  
6. <span data-ttu-id="2234b-115">单击**是**当系统提示你确认该删除的 Microsoft 企业单一登录。</span><span class="sxs-lookup"><span data-stu-id="2234b-115">Click **Yes** when prompted to confirm the removal of Microsoft Enterprise Single Sign-On.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="2234b-116">如果已安装 BizTalk Server 运行时、开发或管理功能，或已安装 Host Integration Server 管理功能，则只有在删除所有依赖项后，才能卸载该 SSO 运行时或管理组件。</span><span class="sxs-lookup"><span data-stu-id="2234b-116">If you have BizTalk Server Runtime, Development, or Administration features installed, or Host Integration Server Administration features installed, you will not be able to uninstall the SSO Runtime or Administration components until all dependencies are removed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2234b-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="2234b-117">See Also</span></span>  
 [<span data-ttu-id="2234b-118">安装 SSO</span><span class="sxs-lookup"><span data-stu-id="2234b-118">Installing SSO</span></span>](../core/installing-sso.md)