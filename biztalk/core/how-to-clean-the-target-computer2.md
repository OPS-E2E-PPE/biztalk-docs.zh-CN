---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-tibco-enterprise-message-service/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 936f25f9dda62cf881b4539a0eee475118294f95
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65342382"
---
# <a name="how-to-clean-the-target-computer"></a><span data-ttu-id="65965-101">如何清理目标计算机</span><span class="sxs-lookup"><span data-stu-id="65965-101">How to Clean the Target Computer</span></span>
<span data-ttu-id="65965-102">部署会覆盖接收位置配置。</span><span class="sxs-lookup"><span data-stu-id="65965-102">Deployment overwrites the receive location configuration.</span></span> <span data-ttu-id="65965-103">当将绑定文件 （和程序集） 部署的目标计算机上，发送端口和接收位置将替换 XML 绑定文件中所导入。</span><span class="sxs-lookup"><span data-stu-id="65965-103">When you deploy a binding file (and assembly) on a target computer, the send ports and receive locations are replaced with those in the XML binding file when they are imported.</span></span>  
  
### <a name="to-clean-the-target-computer"></a><span data-ttu-id="65965-104">若要清理目标计算机</span><span class="sxs-lookup"><span data-stu-id="65965-104">To clean the target computer</span></span>  
  
-   <span data-ttu-id="65965-105">删除任何发送端口和接收位置绑定到业务流程。</span><span class="sxs-lookup"><span data-stu-id="65965-105">Remove any send ports and receive locations bound to the orchestration.</span></span>  
  
     <span data-ttu-id="65965-106">如果没有在目标计算机上安装 Microsoft Visual Studio，则可以通过运行这些脚本删除端口：</span><span class="sxs-lookup"><span data-stu-id="65965-106">If you do not have Microsoft Visual Studio installed on the target computer, you can remove the ports by running these scripts:</span></span>  
  
     <span data-ttu-id="65965-107">\<Microsoft BizTalk Server\>\SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs</span><span class="sxs-lookup"><span data-stu-id="65965-107">\<Microsoft BizTalk Server\>\SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs</span></span>  
  
     <span data-ttu-id="65965-108">\<Microsoft BizTalk Server\>\SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs</span><span class="sxs-lookup"><span data-stu-id="65965-108">\<Microsoft BizTalk Server\>\SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs</span></span>  
  
     <span data-ttu-id="65965-109">例如，在命令提示符下运行：</span><span class="sxs-lookup"><span data-stu-id="65965-109">For example, at a command prompt, run:</span></span>  
  
     <span data-ttu-id="65965-110">**cscript RemoveSendPort.vbs\<发送端口名称\>**</span><span class="sxs-lookup"><span data-stu-id="65965-110">**cscript RemoveSendPort.vbs \<Send port name\>**</span></span>  
  
