---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-peoplesoft-enterprise/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 7f8c87e4d29b06b46b559dccf18c3e1038a34fae
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65332125"
---
# <a name="import-binding-files"></a><span data-ttu-id="62a2e-101">导入绑定文件</span><span class="sxs-lookup"><span data-stu-id="62a2e-101">Import Binding Files</span></span>

## <a name="overview"></a><span data-ttu-id="62a2e-102">概述</span><span class="sxs-lookup"><span data-stu-id="62a2e-102">Overview</span></span>
<span data-ttu-id="62a2e-103">在使用之前[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]要导入绑定文件，请确认以下：</span><span class="sxs-lookup"><span data-stu-id="62a2e-103">Before you use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to import a binding file, verify the following:</span></span>  
  
-   <span data-ttu-id="62a2e-104">CLASSPATH 指向 PeopleSoft 特定文件的特定位置。</span><span class="sxs-lookup"><span data-stu-id="62a2e-104">The CLASSPATH is pointing to a specific location for the PeopleSoft-specific files.</span></span> <span data-ttu-id="62a2e-105">验证这些文件的位置，并在新计算机上相同，或编辑绑定文件。</span><span class="sxs-lookup"><span data-stu-id="62a2e-105">Verify that the location of these files is the same on the new computer—or edit the binding file.</span></span>  
  
-   <span data-ttu-id="62a2e-106">用于响应文件夹必须存在并且可在新计算机上完全相同，或编辑绑定文件。</span><span class="sxs-lookup"><span data-stu-id="62a2e-106">The folders for the responses must exist and be identical on the new computer—or edit the binding file.</span></span>  
  
-   <span data-ttu-id="62a2e-107">PeopleSoft Enterprise 系统密码，如果存在在配置中，将保存为 \* \* \* 绑定文件中。</span><span class="sxs-lookup"><span data-stu-id="62a2e-107">PeopleSoft Enterprise system passwords, if present in the configuration, are saved as \*\*\*\*\* in the binding file.</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="62a2e-108">部署会覆盖接收位置配置。</span><span class="sxs-lookup"><span data-stu-id="62a2e-108">Deployment overwrites receive location configuration.</span></span> <span data-ttu-id="62a2e-109">当部署绑定文件和程序集的目标计算机上，发送端口和接收位置将替换 XML 绑定文件中所导入。</span><span class="sxs-lookup"><span data-stu-id="62a2e-109">When you deploy a binding file and assembly on a target computer, the send ports and receive locations are replaced with those in the XML binding file when they are imported.</span></span>  
  
 <span data-ttu-id="62a2e-110">有关导入绑定文件的分步说明请参阅中的主题"如何为导入绑定到 BizTalk 组"[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]文档。</span><span class="sxs-lookup"><span data-stu-id="62a2e-110">For step-by-step directions about importing binding files, see the topic "How to Import Bindings into a BizTalk Group" in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] documentation.</span></span>  
  
## <a name="clean-the-target-computer"></a><span data-ttu-id="62a2e-111">清理目标计算机</span><span class="sxs-lookup"><span data-stu-id="62a2e-111">Clean the Target Computer</span></span>  
<span data-ttu-id="62a2e-112">若要清理目标计算机部署新应用程序、 删除发送端口和接收位置绑定到业务流程。</span><span class="sxs-lookup"><span data-stu-id="62a2e-112">To clean the target computer for deploying the new application, remove send ports and receive locations bound to the orchestration.</span></span>  
  
<span data-ttu-id="62a2e-113">如果你没有 Microsoft[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]安装在目标计算机上，您可通过运行这些脚本删除端口：</span><span class="sxs-lookup"><span data-stu-id="62a2e-113">If you do not have Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] installed on the target computer, you may remove the ports by running these scripts:</span></span>  
  
<span data-ttu-id="62a2e-114">**\<Microsoft BizTalk Server\>\SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs**</span><span class="sxs-lookup"><span data-stu-id="62a2e-114">**\<Microsoft BizTalk Server\>\SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs**</span></span>  
  
<span data-ttu-id="62a2e-115">**\<Microsoft BizTalk Server\>\SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs**</span><span class="sxs-lookup"><span data-stu-id="62a2e-115">**\<Microsoft BizTalk Server\>\SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs**</span></span>  
  
<span data-ttu-id="62a2e-116">例如，在命令提示符下运行：</span><span class="sxs-lookup"><span data-stu-id="62a2e-116">For example, at a command prompt, run:</span></span>  
  
<span data-ttu-id="62a2e-117">**cscript RemoveSendPort.vbs\<发送端口名称\>**</span><span class="sxs-lookup"><span data-stu-id="62a2e-117">**cscript RemoveSendPort.vbs \<Send port name\>**</span></span>  
  
