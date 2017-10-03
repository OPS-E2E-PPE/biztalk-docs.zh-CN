---
title: "如何在主机上使用跟踪实用程序启动的 SSO |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- host initiated SSO, trace utility
- trace utility
ms.assetid: a53444d1-3f63-42a6-8ee6-b60ff9af9e41
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e00514515b31e79655fe457e1aa8682edf002183
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-use-the-trace-utility-in-host-initiated-sso"></a><span data-ttu-id="243c8-102">如何在主机上使用跟踪实用程序启动的 SSO</span><span class="sxs-lookup"><span data-stu-id="243c8-102">How to Use the Trace Utility in Host Initiated SSO</span></span>
<span data-ttu-id="243c8-103">故障排除的主要方法是跟踪。</span><span class="sxs-lookup"><span data-stu-id="243c8-103">The primary method of troubleshooting is tracing.</span></span>  
  
## <a name="tracing"></a><span data-ttu-id="243c8-104">跟踪</span><span class="sxs-lookup"><span data-stu-id="243c8-104">Tracing</span></span>  
 <span data-ttu-id="243c8-105">使用 Trace 命令行实用工具在 SSO 中启用跟踪。</span><span class="sxs-lookup"><span data-stu-id="243c8-105">Use the Trace command line utility to enable tracing in SSO.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="243c8-106">为了使 trace 命令起作用，文件 tracelog.exe 必须位于以下目录中：</span><span class="sxs-lookup"><span data-stu-id="243c8-106">For the trace command to function, the file tracelog.exe must be in the following directory:</span></span>  
>   
>  <span data-ttu-id="243c8-107">\<*驱动器*>: \program Files\Enterprise 单一登录</span><span class="sxs-lookup"><span data-stu-id="243c8-107">\<*drive*>:\Program Files\Common Files\Enterprise Single Sign-On</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="243c8-108">你可以从以下位置下载此文件： [http://go.microsoft.com/fwlink/?LinkId=59534](http://go.microsoft.com/fwlink/?LinkId=59534)</span><span class="sxs-lookup"><span data-stu-id="243c8-108">You can download this file from the following location: [http://go.microsoft.com/fwlink/?LinkId=59534](http://go.microsoft.com/fwlink/?LinkId=59534)</span></span>  
  
#### <a name="to-use-the-trace-utility"></a><span data-ttu-id="243c8-109">若要使用跟踪实用程序</span><span class="sxs-lookup"><span data-stu-id="243c8-109">To use the trace utility</span></span>  
  
1.  <span data-ttu-id="243c8-110">在 **“开始”** 菜单上，单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="243c8-110">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="243c8-111">在**运行**对话框中，键入**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="243c8-111">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="243c8-112">在命令行上，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="243c8-112">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="243c8-113">默认值是\<驱动器 >: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="243c8-113">The default is \<drive>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="243c8-114">类型**跟踪 – start – 高**若要将跟踪级别设置为高，并开始跟踪。</span><span class="sxs-lookup"><span data-stu-id="243c8-114">Type **Trace –start –high** to set the tracing level to high and begin the trace.</span></span>  
  
5.  <span data-ttu-id="243c8-115">运行主机启动的 SSO 的方案。</span><span class="sxs-lookup"><span data-stu-id="243c8-115">Run the scenario with host initiated SSO.</span></span>  
  
6.  <span data-ttu-id="243c8-116">类型**跟踪 – 停止**结束跟踪。</span><span class="sxs-lookup"><span data-stu-id="243c8-116">Type **Trace –stop** to end the trace.</span></span> <span data-ttu-id="243c8-117">将在上述目录中生成 .bin 文件，可以将其发送到 Microsoft 以进行分析。</span><span class="sxs-lookup"><span data-stu-id="243c8-117">A .bin file is generated in the directory above, which you can send to Microsoft for analysis.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="243c8-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="243c8-118">See Also</span></span>  
 [<span data-ttu-id="243c8-119">主机启动的 SSO</span><span class="sxs-lookup"><span data-stu-id="243c8-119">Host Initiated SSO</span></span>](../core/host-initiated-sso.md)