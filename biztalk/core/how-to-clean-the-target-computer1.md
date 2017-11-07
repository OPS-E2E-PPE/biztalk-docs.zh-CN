---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-tibco-rendezvous/
redirect_document_id: True
ROBOTS: NOINDEX
ms.openlocfilehash: 4ceaef21127ec010450082228b765dcbb8e76005
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
---
# <a name="how-to-clean-the-target-computer"></a><span data-ttu-id="d0760-101">如何清洗目标计算机</span><span class="sxs-lookup"><span data-stu-id="d0760-101">How to Clean the Target Computer</span></span>
<span data-ttu-id="d0760-102">部署将覆盖接收位置配置。</span><span class="sxs-lookup"><span data-stu-id="d0760-102">Deployment overwrites the receive location configuration.</span></span> <span data-ttu-id="d0760-103">当你部署的目标计算机上，发送端口的绑定文件 （和程序集） 和接收位置已替换为 XML 绑定文件中导入时。</span><span class="sxs-lookup"><span data-stu-id="d0760-103">When you deploy a binding file (and assembly) on a target computer, the send ports and receive locations are replaced with those in the XML binding file when they are imported.</span></span>  
  
### <a name="to-clean-the-target-computer"></a><span data-ttu-id="d0760-104">若要清除目标计算机中的</span><span class="sxs-lookup"><span data-stu-id="d0760-104">To clean the target computer</span></span>  
  
-   <span data-ttu-id="d0760-105">删除发送端口和接收位置绑定到业务流程。</span><span class="sxs-lookup"><span data-stu-id="d0760-105">Remove send ports and receive locations bound to the orchestration.</span></span>  
  
     <span data-ttu-id="d0760-106">如果你没有在目标计算机上安装的 Microsoft Visual Studio，你可以通过运行这些脚本中删除的端口：</span><span class="sxs-lookup"><span data-stu-id="d0760-106">If you do not have Microsoft Visual Studio installed on the target computer, you can remove the ports by running these scripts:</span></span>  
  
    -   [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="d0760-107">SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs</span><span class="sxs-lookup"><span data-stu-id="d0760-107">SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs</span></span>  
  
    -   [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="d0760-108">SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs</span><span class="sxs-lookup"><span data-stu-id="d0760-108">SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs</span></span>  
  
         <span data-ttu-id="d0760-109">例如，在命令提示符下运行：</span><span class="sxs-lookup"><span data-stu-id="d0760-109">For example, at a command prompt, run:</span></span>  
  
         <span data-ttu-id="d0760-110">**cscript RemoveSendPort.vbs\<发送端口名称 >**</span><span class="sxs-lookup"><span data-stu-id="d0760-110">**cscript RemoveSendPort.vbs \<Send port name>**</span></span>  
  
