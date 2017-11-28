---
title: "如何帮助安全组件接口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- component interfaces, helping to secure
- security, component interfaces
ms.assetid: 03b2af44-78e7-4fdc-bfa3-7697b2a60986
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 54136aaeae9578ae4e438c5bd8b95b902d618f96
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-help-secure-component-interfaces"></a><span data-ttu-id="257ca-102">如何帮助保护组件接口</span><span class="sxs-lookup"><span data-stu-id="257ca-102">How to Help Secure Component Interfaces</span></span>
<span data-ttu-id="257ca-103">在开始测试组件接口前，必须为它设置安全性。</span><span class="sxs-lookup"><span data-stu-id="257ca-103">Before you can start testing a component interface, you must set up security for it.</span></span> <span data-ttu-id="257ca-104">以下过程描述如何为 PeopleSoft 版本 8.4 配置组件接口安全性，但你可以为版本 8.1 使用过程。</span><span class="sxs-lookup"><span data-stu-id="257ca-104">The following procedure describes how to configure component interface security for PeopleSoft Version 8.4, but you can use the procedure for Version 8.1.</span></span>  
  
### <a name="to-configure-interface-security"></a><span data-ttu-id="257ca-105">配置接口安全性</span><span class="sxs-lookup"><span data-stu-id="257ca-105">To configure interface security</span></span>  
  
1.  <span data-ttu-id="257ca-106">展开**PeopleTools**，展开**安全**，展开**用户配置文件**，然后展开**权限和角色**。</span><span class="sxs-lookup"><span data-stu-id="257ca-106">Expand **PeopleTools**, expand **Security**, expand **User Profiles**, and then expand **Permissions & Roles**.</span></span>  
  
     ![](../core/media/psadapter-47-ps-configsecurity1.gif "PSAdapter_47_PS_ConfigSecurity1")  
  
2.  <span data-ttu-id="257ca-107">单击**权限列表**。</span><span class="sxs-lookup"><span data-stu-id="257ca-107">Click **Permission Lists**.</span></span>  
  
3.  <span data-ttu-id="257ca-108">单击 **“搜索”**。</span><span class="sxs-lookup"><span data-stu-id="257ca-108">Click **Search**.</span></span>  
  
     ![](../core/media/psadapter-48-ps-configsecurity2.gif "PSAdapter_48_PS_ConfigSecurity2")  
  
4.  <span data-ttu-id="257ca-109">在**权限列出搜索**窗格中，选择相关的权限列表。</span><span class="sxs-lookup"><span data-stu-id="257ca-109">In the **Permission Lists Search** pane, select the relevant permission list.</span></span>  
  
     <span data-ttu-id="257ca-110">出现以下窗口。</span><span class="sxs-lookup"><span data-stu-id="257ca-110">The following window appears.</span></span>  
  
     ![](../core/media/psadapter-49-ps-configsecurity3.gif "PSAdapter_49_PS_ConfigSecurity3")  
  
5.  <span data-ttu-id="257ca-111">单击右箭头旁边**登录时间**选项卡以显示更多选项卡。</span><span class="sxs-lookup"><span data-stu-id="257ca-111">Click the right arrow next to the **Sign-on Times** tab to display more tabs.</span></span>  
  
     ![](../core/media/psadapter-50-ps-configsecurity4.gif "PSAdapter_50_PS_ConfigSecurity4")  
  
6.  <span data-ttu-id="257ca-112">单击**组件接口**选项卡。</span><span class="sxs-lookup"><span data-stu-id="257ca-112">Click the **Component Interfaces** tab.</span></span>  
  
7.  <span data-ttu-id="257ca-113">单击 + （加号） 若要向其中添加新行**组件接口**列表。</span><span class="sxs-lookup"><span data-stu-id="257ca-113">Click the + (plus) sign to add a new row to the **Component Interfaces** list.</span></span>  
  
     <span data-ttu-id="257ca-114">出现一个字段，您可在其中键入组件接口名称。</span><span class="sxs-lookup"><span data-stu-id="257ca-114">A field appears in which you can type the component interface name.</span></span>  
  
     ![](../core/media/psadapter-51-ps-configsecurity5.gif "PSAdapter_51_PS_ConfigSecurity5")  
  
8.  <span data-ttu-id="257ca-115">键入组件接口名称，然后单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="257ca-115">Type the component interface name, and then click **Edit**.</span></span>  
  
     <span data-ttu-id="257ca-116">此示例使用组件接口 AR_ITEM_AGENT。</span><span class="sxs-lookup"><span data-stu-id="257ca-116">This example uses component interface AR_ITEM_AGENT.</span></span>  
  
     ![](../core/media/psadapter-52-ps-configsecurity6.gif "PSAdapter_52_PS_ConfigSecurity6")  
  
9. <span data-ttu-id="257ca-117">在列表中，选择每个方法所需的访问级别，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="257ca-117">In the list, select the desired access level for each method, and then click **OK**.</span></span>  
  
     <span data-ttu-id="257ca-118">出现以下窗口。</span><span class="sxs-lookup"><span data-stu-id="257ca-118">The following window appears.</span></span>  
  
     ![](../core/media/psadapter-53-ps-configsecurity7.gif "PSAdapter_53_PS_ConfigSecurity7")  
  
10. <span data-ttu-id="257ca-119">在右窗格中，向下滚动并单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="257ca-119">Scroll down in the right pane, and click **Save**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="257ca-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="257ca-120">See Also</span></span>  
 <span data-ttu-id="257ca-121">[附录 a： 组件接口方法](../core/appendix-a-component-interface-methods.md) </span><span class="sxs-lookup"><span data-stu-id="257ca-121">[Appendix A: Component Interface Methods](../core/appendix-a-component-interface-methods.md) </span></span>  
 [<span data-ttu-id="257ca-122">附录 c： 使用组件接口</span><span class="sxs-lookup"><span data-stu-id="257ca-122">Appendix C: Using Component Interfaces</span></span>](../core/appendix-c-using-component-interfaces.md)