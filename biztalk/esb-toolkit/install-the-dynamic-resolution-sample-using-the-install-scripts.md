---
title: 安装使用安装脚本动态解析示例 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 644b6403-9883-4256-80d5-37881a87ed0e
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 872bb73b9060e25986876c1c2da71afae84b5c52
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25973139"
---
# <a name="install-the-dynamic-resolution-sample-using-the-install-scripts"></a><span data-ttu-id="aaf69-102">安装使用安装脚本动态解析示例</span><span class="sxs-lookup"><span data-stu-id="aaf69-102">Install the Dynamic Resolution Sample Using the Install Scripts</span></span>
<span data-ttu-id="aaf69-103">本部分介绍如何从提供的安装脚本安装动态解析示例[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="aaf69-103">This section describes how you can install the Dynamic Resolution sample from the install scripts provided with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span>  
  
 <span data-ttu-id="aaf69-104">**若要从安装脚本安装动态解析示例**</span><span class="sxs-lookup"><span data-stu-id="aaf69-104">**To install the Dynamic Resolution sample from the install scripts**</span></span>  
  
1.  <span data-ttu-id="aaf69-105">如果你想要执行使用 FTP 的单向消息传送示例，请创建以下 FTP 站点：</span><span class="sxs-lookup"><span data-stu-id="aaf69-105">If you want to execute one-way messaging examples that use FTP, create the following FTP site:</span></span>  
  
    -   <span data-ttu-id="aaf69-106">FTP 虚拟目录名称： 出</span><span class="sxs-lookup"><span data-stu-id="aaf69-106">FTP Virtual Directory name: Out</span></span>  
  
    -   <span data-ttu-id="aaf69-107">位置： \Source\Samples\DynamicResolution\Test\FTP\Out</span><span class="sxs-lookup"><span data-stu-id="aaf69-107">Location: \Source\Samples\DynamicResolution\Test\FTP\Out</span></span>  
  
    -   <span data-ttu-id="aaf69-108">权限： 读取和写入</span><span class="sxs-lookup"><span data-stu-id="aaf69-108">Permissions: Read and Write</span></span>  
  
    -   <span data-ttu-id="aaf69-109">确保 BizTalk 应用程序用户组具有此位置的完全访问权限</span><span class="sxs-lookup"><span data-stu-id="aaf69-109">Ensure the BizTalk Application Users group has full access permission for this location</span></span>  
  
2.  <span data-ttu-id="aaf69-110">如果你想要执行使用 MQSeries 的双向消息传送示例，使用 WebSphere 资源管理器创建以下：</span><span class="sxs-lookup"><span data-stu-id="aaf69-110">If you want to execute two-way messaging examples that use MQSeries, use WebSphere Explorer to create the following:</span></span>  
  
    -   <span data-ttu-id="aaf69-111">具有名称 ESB 队列管理器。DEP。Sample.QueueManager</span><span class="sxs-lookup"><span data-stu-id="aaf69-111">A queue manager with the name ESB.DEP.Sample.QueueManager</span></span>  
  
    -   <span data-ttu-id="aaf69-112">名为测试的队列。OUT ESB 内。DEP。Sample.QueueManager</span><span class="sxs-lookup"><span data-stu-id="aaf69-112">A queue named TEST.OUT within the ESB.DEP.Sample.QueueManager</span></span>  
  
3.  <span data-ttu-id="aaf69-113">在 **“开始”** 菜单上，单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="aaf69-113">On the **Start** menu, click **Run**.</span></span>  
  
4.  <span data-ttu-id="aaf69-114">在**运行**对话框中，键入**cmd**，然后按 ENTER 以打开命令提示符。</span><span class="sxs-lookup"><span data-stu-id="aaf69-114">In the **Run** dialog box, type **cmd**, and then press ENTER to open the command prompt.</span></span>  
  
5.  <span data-ttu-id="aaf69-115">运行以下命令，替换\<路径\>参数替换为你想要安装的.cmd 文件的完整路径 (在此版本中的默认路径是 \Source\Samples\DynamicResolution\Install\Scripts\\):</span><span class="sxs-lookup"><span data-stu-id="aaf69-115">Run the following command, replacing the \<path\> parameter with the full path to the .cmd file you want to install (the default path in this release is \Source\Samples\DynamicResolution\Install\Scripts\\):</span></span>  
  
    ```  
    <path>\Setup_bin.cmd  
    ```