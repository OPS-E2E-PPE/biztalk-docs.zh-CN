---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-peoplesoft-enterprise/
redirect_document_id: True
ROBOTS: NOINDEX
ms.openlocfilehash: 907c21377a6affd5a99576137a5babaa1626c135
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="import-binding-files"></a><span data-ttu-id="fc9cc-101">导入绑定文件</span><span class="sxs-lookup"><span data-stu-id="fc9cc-101">Import Binding Files</span></span>

## <a name="overview"></a><span data-ttu-id="fc9cc-102">概述</span><span class="sxs-lookup"><span data-stu-id="fc9cc-102">Overview</span></span>
<span data-ttu-id="fc9cc-103">在使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 导入绑定文件之前，请验证以下各项：</span><span class="sxs-lookup"><span data-stu-id="fc9cc-103">Before you use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to import a binding file, verify the following:</span></span>  
  
-   <span data-ttu-id="fc9cc-104">CLASSPATH 指向 PeopleSoft 特定文件的特定位置。</span><span class="sxs-lookup"><span data-stu-id="fc9cc-104">The CLASSPATH is pointing to a specific location for the PeopleSoft-specific files.</span></span> <span data-ttu-id="fc9cc-105">验证这些文件的位置是否在新计算机上相同，或编辑绑定文件。</span><span class="sxs-lookup"><span data-stu-id="fc9cc-105">Verify that the location of these files is the same on the new computer—or edit the binding file.</span></span>  
  
-   <span data-ttu-id="fc9cc-106">响应的文件夹必须存在并且可在新计算机上完全相同，或编辑绑定文件。</span><span class="sxs-lookup"><span data-stu-id="fc9cc-106">The folders for the responses must exist and be identical on the new computer—or edit the binding file.</span></span>  
  
-   <span data-ttu-id="fc9cc-107">如果在配置中存在 PeopleSoft Enterprise 系统密码，则在绑定文件中另存为 *****。</span><span class="sxs-lookup"><span data-stu-id="fc9cc-107">PeopleSoft Enterprise system passwords, if present in the configuration, are saved as ***** in the binding file.</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="fc9cc-108">部署会覆盖接收位置配置。</span><span class="sxs-lookup"><span data-stu-id="fc9cc-108">Deployment overwrites receive location configuration.</span></span> <span data-ttu-id="fc9cc-109">如果在目标计算机上部署绑定文件和程序集，则发送端口和接收位置将替换为所导入的 XML 绑定文件中的发送端口和接收位置。</span><span class="sxs-lookup"><span data-stu-id="fc9cc-109">When you deploy a binding file and assembly on a target computer, the send ports and receive locations are replaced with those in the XML binding file when they are imported.</span></span>  
  
 <span data-ttu-id="fc9cc-110">有关导入绑定文件的分步指导信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 文档中的主题“如何将绑定导入到 BizTalk 组”。</span><span class="sxs-lookup"><span data-stu-id="fc9cc-110">For step-by-step directions about importing binding files, see the topic "How to Import Bindings into a BizTalk Group" in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] documentation.</span></span>  
  
## <a name="clean-the-target-computer"></a><span data-ttu-id="fc9cc-111">清除目标计算机中的</span><span class="sxs-lookup"><span data-stu-id="fc9cc-111">Clean the Target Computer</span></span>  
<span data-ttu-id="fc9cc-112">若要清除目标计算机上部署新的应用程序、 删除发送端口和接收位置绑定到业务流程。</span><span class="sxs-lookup"><span data-stu-id="fc9cc-112">To clean the target computer for deploying the new application, remove send ports and receive locations bound to the orchestration.</span></span>  
  
<span data-ttu-id="fc9cc-113">如果没有在目标计算机上安装 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，则可通过运行下面的脚本删除端口：</span><span class="sxs-lookup"><span data-stu-id="fc9cc-113">If you do not have Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] installed on the target computer, you may remove the ports by running these scripts:</span></span>  
  
<span data-ttu-id="fc9cc-114">**\<Microsoft BizTalk Server\>\SDK\Samples\Admin\WMI\Remove 发送 Port\VBScript\RemoveSendPort.vbs**</span><span class="sxs-lookup"><span data-stu-id="fc9cc-114">**\<Microsoft BizTalk Server\>\SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs**</span></span>  
  
<span data-ttu-id="fc9cc-115">**\<Microsoft BizTalk Server\>\SDK\Samples\Admin\WMI\Remove 接收 Port\VBScript\RemoveReceivePort.vbs**</span><span class="sxs-lookup"><span data-stu-id="fc9cc-115">**\<Microsoft BizTalk Server\>\SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs**</span></span>  
  
<span data-ttu-id="fc9cc-116">例如，在命令提示符下运行：</span><span class="sxs-lookup"><span data-stu-id="fc9cc-116">For example, at a command prompt, run:</span></span>  
  
<span data-ttu-id="fc9cc-117">**cscript RemoveSendPort.vbs\<发送端口名称\>**</span><span class="sxs-lookup"><span data-stu-id="fc9cc-117">**cscript RemoveSendPort.vbs \<Send port name\>**</span></span>  
  
