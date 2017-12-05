---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-jd-edwards-enterpriseone/
redirect_document_id: True
ROBOTS: NOINDEX
ms.openlocfilehash: 7dbc9ef8624404b9fa7bdcb7b6a21b2d2a4c69f2
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="importing-binding-files"></a><span data-ttu-id="41856-101">导入绑定文件</span><span class="sxs-lookup"><span data-stu-id="41856-101">Importing Binding Files</span></span>
<span data-ttu-id="41856-102">本主题提供有关导入过程，为博士 Edwards EnterpriseOne 部署的 BizTalk Adapter 时的一些信息。</span><span class="sxs-lookup"><span data-stu-id="41856-102">This topic provides some information concerning the import process when you deploy BizTalk Adapter for JD Edwards EnterpriseOne.</span></span> <span data-ttu-id="41856-103">当你重新绑定文件 （和程序集） 部署的目标计算机上，发送端口和接收位置已替换为 XML 绑定文件中时它们重新导入。</span><span class="sxs-lookup"><span data-stu-id="41856-103">When you redeploy a binding file (and assembly) on a target computer, the send ports and receive locations are replaced with those in the XML binding file when they are reimported.</span></span>  
  
### <a name="to-clean-the-target-computer"></a><span data-ttu-id="41856-104">若要清除目标计算机中的</span><span class="sxs-lookup"><span data-stu-id="41856-104">To clean the target computer</span></span>  
  
-   <span data-ttu-id="41856-105">删除发送端口和接收位置绑定到业务流程。</span><span class="sxs-lookup"><span data-stu-id="41856-105">Remove Send ports and Receive locations bound to the orchestration.</span></span>  
  
     <span data-ttu-id="41856-106">如果未安装目标计算机上安装的 Visual Studio，你可以通过运行脚本中删除的端口：</span><span class="sxs-lookup"><span data-stu-id="41856-106">If you do not have Visual Studio installed on the target computer, you can remove the ports by running the scripts:</span></span>  
  
     [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="41856-107">SDK\Samples\Admin\WMI\\</span><span class="sxs-lookup"><span data-stu-id="41856-107">SDK\Samples\Admin\WMI\\</span></span>  
  
     <span data-ttu-id="41856-108">删除发送 Port\VBScript\RemoveSendPort.vbs</span><span class="sxs-lookup"><span data-stu-id="41856-108">Remove Send Port\VBScript\RemoveSendPort.vbs</span></span>  
  
     [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="41856-109">SDK\Samples\Admin\WMI\\</span><span class="sxs-lookup"><span data-stu-id="41856-109">SDK\Samples\Admin\WMI\\</span></span>  
  
     <span data-ttu-id="41856-110">删除接收 Port\VBScript\RemoveReceivePort.vbs</span><span class="sxs-lookup"><span data-stu-id="41856-110">Remove Receive Port\VBScript\RemoveReceivePort.vbs</span></span>  
  
     <span data-ttu-id="41856-111">例如，从命令提示符下运行：</span><span class="sxs-lookup"><span data-stu-id="41856-111">For example, from a command prompt run:</span></span>  
  
     <span data-ttu-id="41856-112">**cscript RemoveSendPort.vbs\<发送端口名称\>**</span><span class="sxs-lookup"><span data-stu-id="41856-112">**cscript RemoveSendPort.vbs \<Send port name\>**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41856-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="41856-113">See Also</span></span>  
 [<span data-ttu-id="41856-114">导入博士 Edwards EnterpriseOne 应用</span><span class="sxs-lookup"><span data-stu-id="41856-114">Import the JD Edwards EnterpriseOne app</span></span>](../core/deploying-biztalk-adapter-for-jd-edwards-enterpriseone.md)