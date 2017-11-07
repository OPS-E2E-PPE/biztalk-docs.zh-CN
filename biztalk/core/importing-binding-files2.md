---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-jd-edwards-enterpriseone/
redirect_document_id: True
ROBOTS: NOINDEX
ms.openlocfilehash: 0bc5b29ff129b145d6b55cbe44ea3aa6a97def76
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
---
# <a name="importing-binding-files"></a><span data-ttu-id="ff413-101">导入绑定文件</span><span class="sxs-lookup"><span data-stu-id="ff413-101">Importing Binding Files</span></span>
<span data-ttu-id="ff413-102">本主题提供有关导入过程，为博士 Edwards EnterpriseOne 部署的 BizTalk Adapter 时的一些信息。</span><span class="sxs-lookup"><span data-stu-id="ff413-102">This topic provides some information concerning the import process when you deploy BizTalk Adapter for JD Edwards EnterpriseOne.</span></span> <span data-ttu-id="ff413-103">当你重新绑定文件 （和程序集） 部署的目标计算机上，发送端口和接收位置已替换为 XML 绑定文件中时它们重新导入。</span><span class="sxs-lookup"><span data-stu-id="ff413-103">When you redeploy a binding file (and assembly) on a target computer, the send ports and receive locations are replaced with those in the XML binding file when they are reimported.</span></span>  
  
### <a name="to-clean-the-target-computer"></a><span data-ttu-id="ff413-104">若要清除目标计算机中的</span><span class="sxs-lookup"><span data-stu-id="ff413-104">To clean the target computer</span></span>  
  
-   <span data-ttu-id="ff413-105">删除发送端口和接收位置绑定到业务流程。</span><span class="sxs-lookup"><span data-stu-id="ff413-105">Remove Send ports and Receive locations bound to the orchestration.</span></span>  
  
     <span data-ttu-id="ff413-106">如果未安装目标计算机上安装的 Visual Studio，你可以通过运行脚本中删除的端口：</span><span class="sxs-lookup"><span data-stu-id="ff413-106">If you do not have Visual Studio installed on the target computer, you can remove the ports by running the scripts:</span></span>  
  
     [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="ff413-107">SDK\Samples\Admin\WMI\\</span><span class="sxs-lookup"><span data-stu-id="ff413-107">SDK\Samples\Admin\WMI\\</span></span>  
  
     <span data-ttu-id="ff413-108">删除发送 Port\VBScript\RemoveSendPort.vbs</span><span class="sxs-lookup"><span data-stu-id="ff413-108">Remove Send Port\VBScript\RemoveSendPort.vbs</span></span>  
  
     [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="ff413-109">SDK\Samples\Admin\WMI\\</span><span class="sxs-lookup"><span data-stu-id="ff413-109">SDK\Samples\Admin\WMI\\</span></span>  
  
     <span data-ttu-id="ff413-110">删除接收 Port\VBScript\RemoveReceivePort.vbs</span><span class="sxs-lookup"><span data-stu-id="ff413-110">Remove Receive Port\VBScript\RemoveReceivePort.vbs</span></span>  
  
     <span data-ttu-id="ff413-111">例如，从命令提示符下运行：</span><span class="sxs-lookup"><span data-stu-id="ff413-111">For example, from a command prompt run:</span></span>  
  
     <span data-ttu-id="ff413-112">**cscript RemoveSendPort.vbs\<发送端口名称 >**</span><span class="sxs-lookup"><span data-stu-id="ff413-112">**cscript RemoveSendPort.vbs \<Send port name>**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff413-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ff413-113">See Also</span></span>  
 [<span data-ttu-id="ff413-114">导入博士 Edwards EnterpriseOne 应用</span><span class="sxs-lookup"><span data-stu-id="ff413-114">Import the JD Edwards EnterpriseOne app</span></span>](../core/deploying-biztalk-adapter-for-jd-edwards-enterpriseone.md)