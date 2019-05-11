---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-jd-edwards-oneworld/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 920693d0e3ff02b00d8675261db3050f8866b234
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65332171"
---
# <a name="importing-binding-files"></a><span data-ttu-id="1f35f-101">导入绑定文件</span><span class="sxs-lookup"><span data-stu-id="1f35f-101">Importing Binding Files</span></span>

## <a name="overview"></a><span data-ttu-id="1f35f-102">概述</span><span class="sxs-lookup"><span data-stu-id="1f35f-102">Overview</span></span>
<span data-ttu-id="1f35f-103">使用 BizTalk Server 导入绑定文件之前，请验证以下：</span><span class="sxs-lookup"><span data-stu-id="1f35f-103">Before you use the BizTalk Server to import a binding file, verify the following:</span></span>  
  
-   <span data-ttu-id="1f35f-104">CLASSPATH 指向 JD Edwards 特定文件的特定位置。</span><span class="sxs-lookup"><span data-stu-id="1f35f-104">The CLASSPATH is pointing to a specific location for the JD Edwards-specific files.</span></span> <span data-ttu-id="1f35f-105">验证这些文件的位置是相同的新计算机上，或编辑绑定文件。</span><span class="sxs-lookup"><span data-stu-id="1f35f-105">Verify that the location of these files is the same on the new computer, or edit the binding file.</span></span>  
  
-   <span data-ttu-id="1f35f-106">用于响应文件夹存在并在新计算机上完全相同或编辑绑定文件。</span><span class="sxs-lookup"><span data-stu-id="1f35f-106">The folders for the responses exist and are identical on the new computer, or edit the binding file.</span></span>  
  
-   <span data-ttu-id="1f35f-107">JD Edwards 系统密码，如果存在在配置中，将保存为 \* \* \* 绑定文件中。</span><span class="sxs-lookup"><span data-stu-id="1f35f-107">JD Edwards system passwords, if present in the configuration, are saved as \*\*\*\*\* in the binding file.</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="1f35f-108">部署会覆盖接收位置配置。</span><span class="sxs-lookup"><span data-stu-id="1f35f-108">Deployment overwrites Receive Location configuration.</span></span> <span data-ttu-id="1f35f-109">在目标计算机上部署绑定文件 （和程序集），发送端口和接收位置将替换 XML 绑定文件中导入它们。</span><span class="sxs-lookup"><span data-stu-id="1f35f-109">When deploying a binding file (and assembly) on a target computer, the send ports and receive locations are replaced with those in the XML binding file when they are imported.</span></span>  
  
## <a name="import-the-binding-files"></a><span data-ttu-id="1f35f-110">导入绑定文件</span><span class="sxs-lookup"><span data-stu-id="1f35f-110">Import the Binding Files</span></span>  
  
1.  <span data-ttu-id="1f35f-111">上**启动**菜单，依次指向**Program Files**，指向**Microsoft BizTalk Server**，然后单击**BizTalk Server 管理**若要启动 BizTalk Server 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="1f35f-111">On the **Start** menu, point to **Program Files**, point to **Microsoft BizTalk Server**, and then click **BizTalk Server Administration** to start the BizTalk Server Administration Console.</span></span>  
  
2.  <span data-ttu-id="1f35f-112">展开 BizTalk Server 管理，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="1f35f-112">Expand BizTalk Server Administration, expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="1f35f-113">右键单击所需应用程序，指向**导入**，然后单击**绑定**。</span><span class="sxs-lookup"><span data-stu-id="1f35f-113">Right-click the desired application, point to **Import**, and then click **Bindings**.</span></span>  
  
4.  <span data-ttu-id="1f35f-114">在中**导入绑定**对话框中，浏览并选择绑定文件，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="1f35f-114">In the **Import Bindings** dialog box, browse and select the binding files, and then click **Open**.</span></span>  
  
## <a name="cleaning-the-target-computer"></a><span data-ttu-id="1f35f-115">清理目标计算机</span><span class="sxs-lookup"><span data-stu-id="1f35f-115">Cleaning the Target Computer</span></span>  
<span data-ttu-id="1f35f-116">删除发送端口和绑定到业务流程的接收位置。</span><span class="sxs-lookup"><span data-stu-id="1f35f-116">Remove the send ports and the receive locations that are bound to the orchestration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f35f-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="1f35f-117">See Also</span></span>  
 <span data-ttu-id="1f35f-118">[将项目添加到 BizTalk 管理](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md) </span><span class="sxs-lookup"><span data-stu-id="1f35f-118">[Add the artifacts to BizTalk Administration](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md) </span></span>  
 [<span data-ttu-id="1f35f-119">导入 JD Edwards OneWorld 应用程序</span><span class="sxs-lookup"><span data-stu-id="1f35f-119">Import the JD Edwards OneWorld app</span></span>](deploying-biztalk-adapter-for-jd-edwards-oneworld.md)