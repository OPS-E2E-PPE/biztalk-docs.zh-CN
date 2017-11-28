---
title: "步骤 1： 为 Contoso 程序集分配强名称 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- private process tutorial, assigning strong-names
- strong-named assemblies
ms.assetid: c8ec4593-5a4d-47ab-8799-7b2cd3d15ffc
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7124561b9f842a7cc980c7a54230cd122ae32856
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-assigning-a-strong-name-to-the-contoso-assembly"></a><span data-ttu-id="11ad3-102">步骤 1： 为 Contoso 程序集分配强名称</span><span class="sxs-lookup"><span data-stu-id="11ad3-102">Step 1: Assigning a Strong Name to the Contoso Assembly</span></span>
<span data-ttu-id="11ad3-103">在此步骤中，你将为 BizTalk 程序集创建并分配一个强名称。</span><span class="sxs-lookup"><span data-stu-id="11ad3-103">In this step, you create and assign a strong name for your BizTalk assembly.</span></span> <span data-ttu-id="11ad3-104">强名称通过分配一个数字签名和一个唯一的密钥对可确保程序集的唯一性。</span><span class="sxs-lookup"><span data-stu-id="11ad3-104">A strong name guarantees the uniqueness of an assembly by assigning a digital signature and a unique key pair.</span></span> <span data-ttu-id="11ad3-105">此外，强名称还提供了完整性检查以确保自上次构建以来程序集的内容没有发生变化。</span><span class="sxs-lookup"><span data-stu-id="11ad3-105">Additionally, a strong name provides an integrity check to guarantee that the content of the assembly has not changed since you last built it.</span></span>  
  
### <a name="to-create-a-strong-name-assembly-key-file"></a><span data-ttu-id="11ad3-106">创建强名称程序集密钥文件</span><span class="sxs-lookup"><span data-stu-id="11ad3-106">To create a strong name assembly key file</span></span>  
  
1.  <span data-ttu-id="11ad3-107">启动**Visual Studio 2012 的命令提示符**。</span><span class="sxs-lookup"><span data-stu-id="11ad3-107">Start **Visual Studio 2012 Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="11ad3-108">在命令提示符处，转到 Contoso 解决方案的位置。</span><span class="sxs-lookup"><span data-stu-id="11ad3-108">At the command prompt, move to the location of the Contoso solution.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="11ad3-109">默认情况下，Contoso 解决方案的位置是*\<驱动器 >*: \Documents and 设置\\*\<用户名 >*documents\visual Studio \<版本 > \Projects。</span><span class="sxs-lookup"><span data-stu-id="11ad3-109">By default, the location of the Contoso solution is *\<drive>*:\Documents and Settings\\*\<user name>*\My Documents\Visual Studio \<version>\Projects.</span></span>  
  
3.  <span data-ttu-id="11ad3-110">在命令提示符处，键入**sn-k FabConPriceAvail.snk**，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="11ad3-110">At the command prompt, type **sn -k FabConPriceAvail.snk**, and then press **Enter**.</span></span>  
  
4.  <span data-ttu-id="11ad3-111">在命令提示符处，键入**退出**，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="11ad3-111">At the command prompt, type **Exit**, and then press **Enter**.</span></span>  
  
### <a name="to-assign-a-strong-name-to-your-assembly"></a><span data-ttu-id="11ad3-112">指定程序集的强名称</span><span class="sxs-lookup"><span data-stu-id="11ad3-112">To assign a strong name to your assembly</span></span>  
  
1.  <span data-ttu-id="11ad3-113">在解决方案资源管理器，右键单击**ContosoPriceAndAvailability**项目，，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="11ad3-113">In Solution Explorer, right-click the **ContosoPriceAndAvailability** project, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="11ad3-114">在属性页中，单击**签名**的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="11ad3-114">In the Property Pages, click **Signing** in the left pane.</span></span>  
  
3.  <span data-ttu-id="11ad3-115">在右窗格中，选择**对程序集签名**。</span><span class="sxs-lookup"><span data-stu-id="11ad3-115">In the right pane, select **Sign the assembly**.</span></span>  
  
4.  <span data-ttu-id="11ad3-116">单击**浏览**在选择强名称密钥文件字段。</span><span class="sxs-lookup"><span data-stu-id="11ad3-116">Click **Browse** in the Choose the strong name key file field.</span></span>  
  
5.  <span data-ttu-id="11ad3-117">找到你的项目文件夹中，选择**FabConPriceAvail.snk**你之前，创建文件，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="11ad3-117">Locate your project folder, select the **FabConPriceAvail.snk** file you created earlier, and then click **Open**.</span></span>  
  
6.  <span data-ttu-id="11ad3-118">单击**确定**以保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="11ad3-118">Click **OK** to save the changes.</span></span>  
  
7.  <span data-ttu-id="11ad3-119">在解决方案资源管理器，右键单击**ContosoPriceAndAvailability**项目，，然后单击**生成**。</span><span class="sxs-lookup"><span data-stu-id="11ad3-119">In Solution Explorer, right-click the **ContosoPriceAndAvailability** project, and then click **Build**.</span></span> <span data-ttu-id="11ad3-120">已成功生成后，再次右键单击项目，然后单击**部署**。</span><span class="sxs-lookup"><span data-stu-id="11ad3-120">After the build has succeeded, right-click the project again, and then click **Deploy**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11ad3-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="11ad3-121">See Also</span></span>  
 [<span data-ttu-id="11ad3-122">步骤 2： 为 Contoso 3A2 价格和可用性查询/响应方案创建端口</span><span class="sxs-lookup"><span data-stu-id="11ad3-122">Step 2: Creating Ports for the Contoso 3A2 Price and Availability Query/Response Scenario</span></span>](step-2-create-ports-for-contoso-3a2-price-and-availability-query.md)