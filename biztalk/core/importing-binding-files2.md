---
title: "导入绑定 Files2 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- binding files, importing
- assemblies, removing from database
- importing binding files
- target computers, cleaning
- BizTalk assemblies, removing from database
ms.assetid: 9e552a4b-06ec-4887-b17b-a625c137699f
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3783b21385c210c454bcd3d4c951f2200a6ec866
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="importing-binding-files"></a><span data-ttu-id="f2c37-102">导入绑定文件</span><span class="sxs-lookup"><span data-stu-id="f2c37-102">Importing Binding Files</span></span>
<span data-ttu-id="f2c37-103">本主题提供有关导入过程，为博士 Edwards EnterpriseOne 部署的 BizTalk Adapter 时的一些信息。</span><span class="sxs-lookup"><span data-stu-id="f2c37-103">This topic provides some information concerning the import process when you deploy BizTalk Adapter for JD Edwards EnterpriseOne.</span></span> <span data-ttu-id="f2c37-104">当你重新绑定文件 （和程序集） 部署的目标计算机上，发送端口和接收位置已替换为 XML 绑定文件中时它们重新导入。</span><span class="sxs-lookup"><span data-stu-id="f2c37-104">When you redeploy a binding file (and assembly) on a target computer, the send ports and receive locations are replaced with those in the XML binding file when they are reimported.</span></span>  
  
### <a name="to-clean-the-target-computer"></a><span data-ttu-id="f2c37-105">若要清除目标计算机中的</span><span class="sxs-lookup"><span data-stu-id="f2c37-105">To clean the target computer</span></span>  
  
-   <span data-ttu-id="f2c37-106">删除发送端口和接收位置绑定到业务流程。</span><span class="sxs-lookup"><span data-stu-id="f2c37-106">Remove Send ports and Receive locations bound to the orchestration.</span></span>  
  
     <span data-ttu-id="f2c37-107">如果未安装目标计算机上安装的 Visual Studio，你可以通过运行脚本中删除的端口：</span><span class="sxs-lookup"><span data-stu-id="f2c37-107">If you do not have Visual Studio installed on the target computer, you can remove the ports by running the scripts:</span></span>  
  
     [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="f2c37-108">SDK\Samples\Admin\WMI\\</span><span class="sxs-lookup"><span data-stu-id="f2c37-108">SDK\Samples\Admin\WMI\\</span></span>  
  
     <span data-ttu-id="f2c37-109">删除发送 Port\VBScript\RemoveSendPort.vbs</span><span class="sxs-lookup"><span data-stu-id="f2c37-109">Remove Send Port\VBScript\RemoveSendPort.vbs</span></span>  
  
     [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="f2c37-110">SDK\Samples\Admin\WMI\\</span><span class="sxs-lookup"><span data-stu-id="f2c37-110">SDK\Samples\Admin\WMI\\</span></span>  
  
     <span data-ttu-id="f2c37-111">删除接收 Port\VBScript\RemoveReceivePort.vbs</span><span class="sxs-lookup"><span data-stu-id="f2c37-111">Remove Receive Port\VBScript\RemoveReceivePort.vbs</span></span>  
  
     <span data-ttu-id="f2c37-112">例如，从命令提示符下运行：</span><span class="sxs-lookup"><span data-stu-id="f2c37-112">For example, from a command prompt run:</span></span>  
  
     <span data-ttu-id="f2c37-113">**cscript RemoveSendPort.vbs\<发送端口名称 >**</span><span class="sxs-lookup"><span data-stu-id="f2c37-113">**cscript RemoveSendPort.vbs \<Send port name>**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2c37-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f2c37-114">See Also</span></span>  
 [<span data-ttu-id="f2c37-115">部署端口和程序集</span><span class="sxs-lookup"><span data-stu-id="f2c37-115">Deploying Ports and Assemblies</span></span>](../core/deploying-ports-and-assemblies3.md)