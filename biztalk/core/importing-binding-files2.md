---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-jd-edwards-enterpriseone/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: db28e1db8a0f2d4149e0539e2bce195cd91b1279
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973982"
---
# <a name="importing-binding-files"></a><span data-ttu-id="3d5ef-101">导入绑定文件</span><span class="sxs-lookup"><span data-stu-id="3d5ef-101">Importing Binding Files</span></span>
<span data-ttu-id="3d5ef-102">本主题提供有关导入过程，在部署用于 JD Edwards EnterpriseOne 的 BizTalk 适配器时的一些信息。</span><span class="sxs-lookup"><span data-stu-id="3d5ef-102">This topic provides some information concerning the import process when you deploy BizTalk Adapter for JD Edwards EnterpriseOne.</span></span> <span data-ttu-id="3d5ef-103">当重新绑定文件 （和程序集） 部署的目标计算机上，发送端口和接收位置将替换中的 XML 绑定文件时它们重新导入。</span><span class="sxs-lookup"><span data-stu-id="3d5ef-103">When you redeploy a binding file (and assembly) on a target computer, the send ports and receive locations are replaced with those in the XML binding file when they are reimported.</span></span>  
  
### <a name="to-clean-the-target-computer"></a><span data-ttu-id="3d5ef-104">若要清理目标计算机</span><span class="sxs-lookup"><span data-stu-id="3d5ef-104">To clean the target computer</span></span>  
  
- <span data-ttu-id="3d5ef-105">删除发送端口和接收位置绑定到业务流程。</span><span class="sxs-lookup"><span data-stu-id="3d5ef-105">Remove Send ports and Receive locations bound to the orchestration.</span></span>  
  
   <span data-ttu-id="3d5ef-106">如果未安装目标计算机上安装的 Visual Studio，则可以通过运行脚本删除端口：</span><span class="sxs-lookup"><span data-stu-id="3d5ef-106">If you do not have Visual Studio installed on the target computer, you can remove the ports by running the scripts:</span></span>  
  
   [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="3d5ef-107">SDK\Samples\Admin\WMI\\</span><span class="sxs-lookup"><span data-stu-id="3d5ef-107">SDK\Samples\Admin\WMI\\</span></span>  
  
   <span data-ttu-id="3d5ef-108">删除发送 Port\VBScript\RemoveSendPort.vbs</span><span class="sxs-lookup"><span data-stu-id="3d5ef-108">Remove Send Port\VBScript\RemoveSendPort.vbs</span></span>  
  
   [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="3d5ef-109">SDK\Samples\Admin\WMI\\</span><span class="sxs-lookup"><span data-stu-id="3d5ef-109">SDK\Samples\Admin\WMI\\</span></span>  
  
   <span data-ttu-id="3d5ef-110">删除接收 Port\VBScript\RemoveReceivePort.vbs</span><span class="sxs-lookup"><span data-stu-id="3d5ef-110">Remove Receive Port\VBScript\RemoveReceivePort.vbs</span></span>  
  
   <span data-ttu-id="3d5ef-111">例如，从命令提示符下运行：</span><span class="sxs-lookup"><span data-stu-id="3d5ef-111">For example, from a command prompt run:</span></span>  
  
   <span data-ttu-id="3d5ef-112">**cscript RemoveSendPort.vbs\<发送端口名称\>**</span><span class="sxs-lookup"><span data-stu-id="3d5ef-112">**cscript RemoveSendPort.vbs \<Send port name\>**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d5ef-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="3d5ef-113">See Also</span></span>  
 [<span data-ttu-id="3d5ef-114">导入 JD Edwards EnterpriseOne 应用程序</span><span class="sxs-lookup"><span data-stu-id="3d5ef-114">Import the JD Edwards EnterpriseOne app</span></span>](../core/deploying-biztalk-adapter-for-jd-edwards-enterpriseone.md)