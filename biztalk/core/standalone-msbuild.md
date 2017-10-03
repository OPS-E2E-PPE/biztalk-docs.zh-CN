---
title: "独立 MSBUILD |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 21aa3693-3788-4874-b506-6f4584fb4fd5
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 584d9d5fa8e0c0f6be64d3761fabe45cd08e5a26
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="standalone-msbuild"></a><span data-ttu-id="978c2-102">独立 MSBUILD</span><span class="sxs-lookup"><span data-stu-id="978c2-102">Standalone MSBUILD</span></span>
<span data-ttu-id="978c2-103">**项目生成**组件的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]可用于构建[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]不包含解决方案[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="978c2-103">The **Project Build** component of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] allows you to build [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] solutions without [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="978c2-104">若要安装**项目生成**组件在服务器上，选择**项目生成组件**选项**其他软件类别**在安装过程。</span><span class="sxs-lookup"><span data-stu-id="978c2-104">To install the **Project Build** component on your server, select the **Project Build Component** option in the **Additional Software category** during installation.</span></span> <span data-ttu-id="978c2-105">应取消选中**开发人员工具和 SDK**如要安装[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]没有的计算机上[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="978c2-105">You should unselect the **Developer Tools and SDK** as you are installing [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] on a computer without [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
 <span data-ttu-id="978c2-106">有关 MSBUILD 的详细信息，请参阅[http://go.microsoft.com/fwlink/?LinkId=193567](http://go.microsoft.com/fwlink/?LinkId=193567)。</span><span class="sxs-lookup"><span data-stu-id="978c2-106">For more information on MSBUILD, see [http://go.microsoft.com/fwlink/?LinkId=193567](http://go.microsoft.com/fwlink/?LinkId=193567).</span></span>  
  
## <a name="to-build-a-biztalk-project"></a><span data-ttu-id="978c2-107">若要生成 BizTalk 项目</span><span class="sxs-lookup"><span data-stu-id="978c2-107">To build a BizTalk project</span></span>  
  
1.  <span data-ttu-id="978c2-108">单击 **“开始”**，再单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="978c2-108">Click **Start**, and click **Run**.</span></span>  
  
2.  <span data-ttu-id="978c2-109">类型**cmd**，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="978c2-109">Type **cmd**, and press ENTER.</span></span>  
  
3.  <span data-ttu-id="978c2-110">切换到项目目录，然后运行 MSBUILD 命令以生成 BizTalk 解决方案。</span><span class="sxs-lookup"><span data-stu-id="978c2-110">Switch to the project directory, and run a MSBUILD command to build the BizTalk solution.</span></span>  
  
    ```  
    msbuild unittesttest.sln /p:Configuration=Debug  
    ```  
  
    > [!TIP]
    >  <span data-ttu-id="978c2-111">你可能需要设置 PATH 环境变量，以指向的文件夹中的 msbuild.exe 驻留 (\<*windows 安装目录*> \Microsoft.NET\Framework\v4)。</span><span class="sxs-lookup"><span data-stu-id="978c2-111">You may need set the PATH environment variable to point to the folder in which msbuild.exe resides (\<*windows installation directory*>\Microsoft.NET\Framework\v4).</span></span>