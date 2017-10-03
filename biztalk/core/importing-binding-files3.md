---
title: "导入绑定 Files3 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- binding files, importing
- target computer, cleaning
- importing binding files
- cleaning target computer
ms.assetid: 955bb3e1-3dbc-43ce-9126-205d838ae662
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa1d95c40e3e556068e15a269ee4cbb7e995429a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="importing-binding-files"></a><span data-ttu-id="060b7-102">导入绑定文件</span><span class="sxs-lookup"><span data-stu-id="060b7-102">Importing Binding Files</span></span>
<span data-ttu-id="060b7-103">BizTalk Server 用于导入绑定文件之前，请验证以下各项：</span><span class="sxs-lookup"><span data-stu-id="060b7-103">Before you use the BizTalk Server to import a binding file, verify the following:</span></span>  
  
-   <span data-ttu-id="060b7-104">CLASSPATH 指向 JD Edwards 特定文件的特定位置。</span><span class="sxs-lookup"><span data-stu-id="060b7-104">The CLASSPATH is pointing to a specific location for the JD Edwards-specific files.</span></span> <span data-ttu-id="060b7-105">验证在新计算机上这些文件的位置是否相同，否则编辑绑定文件。</span><span class="sxs-lookup"><span data-stu-id="060b7-105">Verify that the location of these files is the same on the new computer, or edit the binding file.</span></span>  
  
-   <span data-ttu-id="060b7-106">用于响应的文件夹存在，并且在新计算机上相同，否则编辑绑定文件。</span><span class="sxs-lookup"><span data-stu-id="060b7-106">The folders for the responses exist and are identical on the new computer, or edit the binding file.</span></span>  
  
-   <span data-ttu-id="060b7-107">如果在配置中存在 JD Edwards 系统密码，则在绑定文件中另存为 *****。</span><span class="sxs-lookup"><span data-stu-id="060b7-107">JD Edwards system passwords, if present in the configuration, are saved as ***** in the binding file.</span></span> <span data-ttu-id="060b7-108">有关详细信息，请参阅[部署限制](../core/deployment-limitations2.md)。</span><span class="sxs-lookup"><span data-stu-id="060b7-108">For more information, see [Deployment Limitations](../core/deployment-limitations2.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="060b7-109">部署将覆盖接收位置配置。</span><span class="sxs-lookup"><span data-stu-id="060b7-109">Deployment overwrites Receive Location configuration.</span></span> <span data-ttu-id="060b7-110">如果在目标计算机上部署绑定文件（和程序集），则发送端口和接收位置将替换为所导入的 XML 绑定文件中的发送端口和接收位置。</span><span class="sxs-lookup"><span data-stu-id="060b7-110">When deploying a binding file (and assembly) on a target computer, the send ports and receive locations are replaced with those in the XML binding file when they are imported.</span></span>  
  
## <a name="importing-the-binding-files"></a><span data-ttu-id="060b7-111">导入绑定文件</span><span class="sxs-lookup"><span data-stu-id="060b7-111">Importing the Binding Files</span></span>  
 <span data-ttu-id="060b7-112">使用以下过程导入绑定文件。</span><span class="sxs-lookup"><span data-stu-id="060b7-112">Use the following procedure to import the binding files.</span></span>  
  
#### <a name="to-import-the-binding-files"></a><span data-ttu-id="060b7-113">导入绑定文件</span><span class="sxs-lookup"><span data-stu-id="060b7-113">To import the binding files</span></span>  
  
1.  <span data-ttu-id="060b7-114">上**启动**菜单上，指向**Program Files**，指向**Microsoft BizTalk Server**，然后单击**BizTalk Server 管理**若要启动 BizTalk Server 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="060b7-114">On the **Start** menu, point to **Program Files**, point to **Microsoft BizTalk Server**, and then click **BizTalk Server Administration** to start the BizTalk Server Administration Console.</span></span>  
  
2.  <span data-ttu-id="060b7-115">展开 BizTalk Server 管理中，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="060b7-115">Expand BizTalk Server Administration, expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="060b7-116">右键单击所需应用程序，指向**导入**，然后单击**绑定**。</span><span class="sxs-lookup"><span data-stu-id="060b7-116">Right-click the desired application, point to **Import**, and then click **Bindings**.</span></span>  
  
4.  <span data-ttu-id="060b7-117">在**导入绑定**对话框中，浏览并选择绑定文件，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="060b7-117">In the **Import Bindings** dialog box, browse and select the binding files, and then click **Open**.</span></span>  
  
## <a name="cleaning-the-target-computer"></a><span data-ttu-id="060b7-118">清理目标计算机</span><span class="sxs-lookup"><span data-stu-id="060b7-118">Cleaning the Target Computer</span></span>  
 <span data-ttu-id="060b7-119">使用以下过程清理目标计算机。</span><span class="sxs-lookup"><span data-stu-id="060b7-119">Use the following procedure to clean the target computer.</span></span>  
  
#### <a name="to-clean-the-target-computer"></a><span data-ttu-id="060b7-120">若要清除目标计算机中的</span><span class="sxs-lookup"><span data-stu-id="060b7-120">To clean the target computer</span></span>  
  
-   <span data-ttu-id="060b7-121">删除发送端口和绑定到业务流程的接收位置。</span><span class="sxs-lookup"><span data-stu-id="060b7-121">Remove the send ports and the receive locations that are bound to the orchestration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="060b7-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="060b7-122">See Also</span></span>  
 <span data-ttu-id="060b7-123">[创建博士 Edwards OneWorld 发送处理程序](../core/creating-jd-edwards-oneworld-send-handlers.md) </span><span class="sxs-lookup"><span data-stu-id="060b7-123">[Creating JD Edwards OneWorld Send Handlers](../core/creating-jd-edwards-oneworld-send-handlers.md) </span></span>  
 [<span data-ttu-id="060b7-124">部署端口和程序集</span><span class="sxs-lookup"><span data-stu-id="060b7-124">Deploying Ports and Assemblies</span></span>](../core/deploying-ports-and-assemblies4.md)