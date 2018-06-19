---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-jd-edwards-oneworld/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 5c5cce40f3fbeb580ec7ba854d02cb243e1742b4
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
ms.locfileid: "24013460"
---
# <a name="importing-binding-files"></a><span data-ttu-id="5b013-101">导入绑定文件</span><span class="sxs-lookup"><span data-stu-id="5b013-101">Importing Binding Files</span></span>

## <a name="overview"></a><span data-ttu-id="5b013-102">概述</span><span class="sxs-lookup"><span data-stu-id="5b013-102">Overview</span></span>
<span data-ttu-id="5b013-103">BizTalk Server 用于导入绑定文件之前，请验证以下各项：</span><span class="sxs-lookup"><span data-stu-id="5b013-103">Before you use the BizTalk Server to import a binding file, verify the following:</span></span>  
  
-   <span data-ttu-id="5b013-104">CLASSPATH 指向 JD Edwards 特定文件的特定位置。</span><span class="sxs-lookup"><span data-stu-id="5b013-104">The CLASSPATH is pointing to a specific location for the JD Edwards-specific files.</span></span> <span data-ttu-id="5b013-105">验证在新计算机上这些文件的位置是否相同，否则编辑绑定文件。</span><span class="sxs-lookup"><span data-stu-id="5b013-105">Verify that the location of these files is the same on the new computer, or edit the binding file.</span></span>  
  
-   <span data-ttu-id="5b013-106">用于响应的文件夹存在，并且在新计算机上相同，否则编辑绑定文件。</span><span class="sxs-lookup"><span data-stu-id="5b013-106">The folders for the responses exist and are identical on the new computer, or edit the binding file.</span></span>  
  
-   <span data-ttu-id="5b013-107">如果在配置中存在 JD Edwards 系统密码，则在绑定文件中另存为 \*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5b013-107">JD Edwards system passwords, if present in the configuration, are saved as \*\*\*\*\* in the binding file.</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="5b013-108">部署将覆盖接收位置配置。</span><span class="sxs-lookup"><span data-stu-id="5b013-108">Deployment overwrites Receive Location configuration.</span></span> <span data-ttu-id="5b013-109">如果在目标计算机上部署绑定文件（和程序集），则发送端口和接收位置将替换为所导入的 XML 绑定文件中的发送端口和接收位置。</span><span class="sxs-lookup"><span data-stu-id="5b013-109">When deploying a binding file (and assembly) on a target computer, the send ports and receive locations are replaced with those in the XML binding file when they are imported.</span></span>  
  
## <a name="import-the-binding-files"></a><span data-ttu-id="5b013-110">导入的绑定文件</span><span class="sxs-lookup"><span data-stu-id="5b013-110">Import the Binding Files</span></span>  
  
1.  <span data-ttu-id="5b013-111">上**启动**菜单上，指向**Program Files**，指向**Microsoft BizTalk Server**，然后单击**BizTalk Server 管理**若要启动 BizTalk Server 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="5b013-111">On the **Start** menu, point to **Program Files**, point to **Microsoft BizTalk Server**, and then click **BizTalk Server Administration** to start the BizTalk Server Administration Console.</span></span>  
  
2.  <span data-ttu-id="5b013-112">展开 BizTalk Server 管理中，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="5b013-112">Expand BizTalk Server Administration, expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="5b013-113">右键单击所需应用程序，指向**导入**，然后单击**绑定**。</span><span class="sxs-lookup"><span data-stu-id="5b013-113">Right-click the desired application, point to **Import**, and then click **Bindings**.</span></span>  
  
4.  <span data-ttu-id="5b013-114">在**导入绑定**对话框中，浏览并选择绑定文件，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="5b013-114">In the **Import Bindings** dialog box, browse and select the binding files, and then click **Open**.</span></span>  
  
## <a name="cleaning-the-target-computer"></a><span data-ttu-id="5b013-115">清理目标计算机</span><span class="sxs-lookup"><span data-stu-id="5b013-115">Cleaning the Target Computer</span></span>  
<span data-ttu-id="5b013-116">删除发送端口和绑定到业务流程的接收位置。</span><span class="sxs-lookup"><span data-stu-id="5b013-116">Remove the send ports and the receive locations that are bound to the orchestration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b013-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5b013-117">See Also</span></span>  
 <span data-ttu-id="5b013-118">[将项目添加到 BizTalk 管理](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md) </span><span class="sxs-lookup"><span data-stu-id="5b013-118">[Add the artifacts to BizTalk Administration](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md) </span></span>  
 [<span data-ttu-id="5b013-119">导入博士 Edwards OneWorld 应用</span><span class="sxs-lookup"><span data-stu-id="5b013-119">Import the JD Edwards OneWorld app</span></span>](deploying-biztalk-adapter-for-jd-edwards-oneworld.md)