---
title: "如何清洗目标 Computer2 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: cleaning target computer
ms.assetid: 0d25930e-0bee-4658-80e7-4a1ab4a8131d
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b15614af9a42489693d535896245254208379d76
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-clean-the-target-computer"></a><span data-ttu-id="9f54e-102">如何清洗目标计算机</span><span class="sxs-lookup"><span data-stu-id="9f54e-102">How to Clean the Target Computer</span></span>
<span data-ttu-id="9f54e-103">部署将覆盖接收位置配置。</span><span class="sxs-lookup"><span data-stu-id="9f54e-103">Deployment overwrites the receive location configuration.</span></span> <span data-ttu-id="9f54e-104">当你部署的目标计算机上，发送端口的绑定文件 （和程序集） 和接收位置已替换为 XML 绑定文件中导入时。</span><span class="sxs-lookup"><span data-stu-id="9f54e-104">When you deploy a binding file (and assembly) on a target computer, the send ports and receive locations are replaced with those in the XML binding file when they are imported.</span></span>  
  
### <a name="to-clean-the-target-computer"></a><span data-ttu-id="9f54e-105">若要清除目标计算机中的</span><span class="sxs-lookup"><span data-stu-id="9f54e-105">To clean the target computer</span></span>  
  
-   <span data-ttu-id="9f54e-106">删除与业务流程绑定的所有发送端口和接收位置。</span><span class="sxs-lookup"><span data-stu-id="9f54e-106">Remove any send ports and receive locations bound to the orchestration.</span></span>  
  
     <span data-ttu-id="9f54e-107">如果你没有在目标计算机上安装的 Microsoft Visual Studio，你可以通过运行这些脚本中删除的端口：</span><span class="sxs-lookup"><span data-stu-id="9f54e-107">If you do not have Microsoft Visual Studio installed on the target computer, you can remove the ports by running these scripts:</span></span>  
  
     <span data-ttu-id="9f54e-108">\<Microsoft BizTalk Server > \SDK\Samples\Admin\WMI\Remove 发送 Port\VBScript\RemoveSendPort.vbs</span><span class="sxs-lookup"><span data-stu-id="9f54e-108">\<Microsoft BizTalk Server>\SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs</span></span>  
  
     <span data-ttu-id="9f54e-109">\<Microsoft BizTalk Server > \SDK\Samples\Admin\WMI\Remove 接收 Port\VBScript\RemoveReceivePort.vbs</span><span class="sxs-lookup"><span data-stu-id="9f54e-109">\<Microsoft BizTalk Server>\SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs</span></span>  
  
     <span data-ttu-id="9f54e-110">例如，在命令提示符下运行：</span><span class="sxs-lookup"><span data-stu-id="9f54e-110">For example, at a command prompt, run:</span></span>  
  
     <span data-ttu-id="9f54e-111">**cscript RemoveSendPort.vbs\<发送端口名称 >**</span><span class="sxs-lookup"><span data-stu-id="9f54e-111">**cscript RemoveSendPort.vbs \<Send port name>**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f54e-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9f54e-112">See Also</span></span>  
 [<span data-ttu-id="9f54e-113">部署端口和程序集</span><span class="sxs-lookup"><span data-stu-id="9f54e-113">Deploying Ports and Assemblies</span></span>](../core/deploying-ports-and-assemblies2.md)