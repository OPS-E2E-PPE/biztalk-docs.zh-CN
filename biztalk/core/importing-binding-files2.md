---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-jd-edwards-enterpriseone/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: d21d4eaf70948d304564d64379ebd834e89df4ce
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382501"
---
# <a name="importing-binding-files"></a><span data-ttu-id="f99c6-101">导入绑定文件</span><span class="sxs-lookup"><span data-stu-id="f99c6-101">Importing Binding Files</span></span>
<span data-ttu-id="f99c6-102">本主题提供有关导入过程，在部署用于 JD Edwards EnterpriseOne 的 BizTalk 适配器时的一些信息。</span><span class="sxs-lookup"><span data-stu-id="f99c6-102">This topic provides some information concerning the import process when you deploy BizTalk Adapter for JD Edwards EnterpriseOne.</span></span> <span data-ttu-id="f99c6-103">当重新绑定文件 （和程序集） 部署的目标计算机上，发送端口和接收位置将替换中的 XML 绑定文件时它们重新导入。</span><span class="sxs-lookup"><span data-stu-id="f99c6-103">When you redeploy a binding file (and assembly) on a target computer, the send ports and receive locations are replaced with those in the XML binding file when they are reimported.</span></span>  
  
### <a name="to-clean-the-target-computer"></a><span data-ttu-id="f99c6-104">若要清理目标计算机</span><span class="sxs-lookup"><span data-stu-id="f99c6-104">To clean the target computer</span></span>  
  
- <span data-ttu-id="f99c6-105">删除发送端口和接收位置绑定到业务流程。</span><span class="sxs-lookup"><span data-stu-id="f99c6-105">Remove Send ports and Receive locations bound to the orchestration.</span></span>  
  
   <span data-ttu-id="f99c6-106">如果未安装目标计算机上安装的 Visual Studio，则可以通过运行脚本删除端口：</span><span class="sxs-lookup"><span data-stu-id="f99c6-106">If you do not have Visual Studio installed on the target computer, you can remove the ports by running the scripts:</span></span>  
  
   [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="f99c6-107">SDK\Samples\Admin\WMI\\</span><span class="sxs-lookup"><span data-stu-id="f99c6-107">SDK\Samples\Admin\WMI\\</span></span>  
  
   <span data-ttu-id="f99c6-108">Remove Send Port\VBScript\RemoveSendPort.vbs</span><span class="sxs-lookup"><span data-stu-id="f99c6-108">Remove Send Port\VBScript\RemoveSendPort.vbs</span></span>  
  
   [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="f99c6-109">SDK\Samples\Admin\WMI\\</span><span class="sxs-lookup"><span data-stu-id="f99c6-109">SDK\Samples\Admin\WMI\\</span></span>  
  
   <span data-ttu-id="f99c6-110">Remove Receive Port\VBScript\RemoveReceivePort.vbs</span><span class="sxs-lookup"><span data-stu-id="f99c6-110">Remove Receive Port\VBScript\RemoveReceivePort.vbs</span></span>  
  
   <span data-ttu-id="f99c6-111">例如，在命令提示符下运行：</span><span class="sxs-lookup"><span data-stu-id="f99c6-111">For example, from a command prompt run:</span></span>  
  
   <span data-ttu-id="f99c6-112">**cscript RemoveSendPort.vbs\<发送端口名称\>**</span><span class="sxs-lookup"><span data-stu-id="f99c6-112">**cscript RemoveSendPort.vbs \<Send port name\>**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f99c6-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="f99c6-113">See Also</span></span>  
 [<span data-ttu-id="f99c6-114">导入 JD Edwards EnterpriseOne 应用程序</span><span class="sxs-lookup"><span data-stu-id="f99c6-114">Import the JD Edwards EnterpriseOne app</span></span>](../core/deploying-biztalk-adapter-for-jd-edwards-enterpriseone.md)