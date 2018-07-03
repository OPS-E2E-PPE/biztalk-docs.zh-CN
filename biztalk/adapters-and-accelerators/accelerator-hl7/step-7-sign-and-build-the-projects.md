---
title: 步骤 7： 登录和生成项目 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message enrichment tutorial, projects
- projects, building
- projects, signing
ms.assetid: b66e4dc1-4ec6-4ec0-a69a-419b116b19c1
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b34ad40b7ee8e083f53e18c34e65fa3c8699d352
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970118"
---
# <a name="step-7-sign-and-build-the-projects"></a><span data-ttu-id="f4ce9-102">步骤 7： 登录和生成项目</span><span class="sxs-lookup"><span data-stu-id="f4ce9-102">Step 7: Sign and Build the Projects</span></span>
<span data-ttu-id="f4ce9-103">在此步骤中，指定一个强名称和生成项目以生成包含你在中创建的资源 （架构） 的程序集[第 6 步： 验证架构](../../adapters-and-accelerators/accelerator-hl7/step-6-validate-the-schemas.md)。</span><span class="sxs-lookup"><span data-stu-id="f4ce9-103">In this step, you assign a strong name and build the project to generate an assembly that contains the resources (the schema) that you created in [Step 6: Validate the Schemas](../../adapters-and-accelerators/accelerator-hl7/step-6-validate-the-schemas.md).</span></span> <span data-ttu-id="f4ce9-104">这还可确保到目前为止完成的工作中没有任何编译错误。</span><span class="sxs-lookup"><span data-stu-id="f4ce9-104">This also ensures that there are no compile errors in the work you have completed so far.</span></span>  
  
### <a name="to-sign-the-btahl7-project"></a><span data-ttu-id="f4ce9-105">若要登录 BTAHL7 项目</span><span class="sxs-lookup"><span data-stu-id="f4ce9-105">To sign the BTAHL7 Project</span></span>  
  
1.  <span data-ttu-id="f4ce9-106">在解决方案资源管理器中右键单击**BTAHL7 项目**，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="f4ce9-106">In Solution Explorer, right-click **BTAHL7 Project**, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="f4ce9-107">在 BTAHL7 项目属性页对话框中，单击**程序集**。</span><span class="sxs-lookup"><span data-stu-id="f4ce9-107">In the BTAHL7 Project Property Pages dialog box, click **Assembly**.</span></span>  
  
3.  <span data-ttu-id="f4ce9-108">在右窗格中，向下滚动到**强名称**部分中，单击右侧的字段**程序集密钥文件**，然后单击省略号 （...） 按钮。</span><span class="sxs-lookup"><span data-stu-id="f4ce9-108">In the right pane, scroll down to the **Strong name** section, click the field to the right of **Assembly Key File**, and then click the ellipsis (…) button.</span></span>  
  
4.  <span data-ttu-id="f4ce9-109">在程序集密钥文件对话框中，浏览到 **\<*驱动器*\>: \Tutorial\BTAHL7V22Common\key.snk** (在创建[步骤 3： 分配强名称程序集](../../adapters-and-accelerators/accelerator-hl7/step-3-assign-a-strong-name-to-the-assembly.md))，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="f4ce9-109">In the Assembly Key File dialog box, browse to **\<*drive*\>:\Tutorial\BTAHL7V22Common\key.snk** (as created in [Step 3: Assign a Strong Name to the Assembly](../../adapters-and-accelerators/accelerator-hl7/step-3-assign-a-strong-name-to-the-assembly.md)), and then click **Open**.</span></span>  
  
5.  <span data-ttu-id="f4ce9-110">单击**确定**以保存更改。</span><span class="sxs-lookup"><span data-stu-id="f4ce9-110">Click **OK** to save changes.</span></span>  
  
### <a name="to-build-the-btahl7-project"></a><span data-ttu-id="f4ce9-111">若要生成 BTAHL7 项目</span><span class="sxs-lookup"><span data-stu-id="f4ce9-111">To build the BTAHL7 Project</span></span>  
  
- <span data-ttu-id="f4ce9-112">在解决方案资源管理器中右键单击**BTAHL7 项目**，然后单击**部署**。</span><span class="sxs-lookup"><span data-stu-id="f4ce9-112">In Solution Explorer, right-click **BTAHL7 Project**, and then click **Deploy**.</span></span> [!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)]<span data-ttu-id="f4ce9-113"> 编译到 DLL 文件的程序集，并将其保存在\<*驱动器*\>: \Tutorial\BTAHL7V22Common\Bin\Development 文件夹。</span><span class="sxs-lookup"><span data-stu-id="f4ce9-113"> compiles the assembly into a DLL file and saves it in the \<*drive*\>:\Tutorial\BTAHL7V22Common\Bin\Development folder.</span></span>  
  
  <span data-ttu-id="f4ce9-114">请继续执行[步骤 8： 使用 BizTalk 映射器创建映射](../../adapters-and-accelerators/accelerator-hl7/step-8-create-a-map-with-biztalk-mapper.md)。</span><span class="sxs-lookup"><span data-stu-id="f4ce9-114">Proceed to [Step 8: Create a Map with BizTalk Mapper](../../adapters-and-accelerators/accelerator-hl7/step-8-create-a-map-with-biztalk-mapper.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4ce9-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="f4ce9-115">See Also</span></span>  
 [<span data-ttu-id="f4ce9-116">消息充实教程</span><span class="sxs-lookup"><span data-stu-id="f4ce9-116">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)