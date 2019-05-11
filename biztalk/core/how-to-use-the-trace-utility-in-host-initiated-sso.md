---
title: 如何在主机中使用跟踪实用工具启动的 SSO |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- host initiated SSO, trace utility
- trace utility
ms.assetid: a53444d1-3f63-42a6-8ee6-b60ff9af9e41
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed0b0a77881cba6de26454f51c6f6f8e21103e90
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333173"
---
# <a name="how-to-use-the-trace-utility-in-host-initiated-sso"></a><span data-ttu-id="64920-102">如何在主机中使用跟踪实用工具启动的 SSO</span><span class="sxs-lookup"><span data-stu-id="64920-102">How to Use the Trace Utility in Host Initiated SSO</span></span>
<span data-ttu-id="64920-103">故障排除的主要方法跟踪。</span><span class="sxs-lookup"><span data-stu-id="64920-103">The primary method of troubleshooting is tracing.</span></span>  
  
## <a name="tracing"></a><span data-ttu-id="64920-104">跟踪</span><span class="sxs-lookup"><span data-stu-id="64920-104">Tracing</span></span>  
 <span data-ttu-id="64920-105">使用 Trace 命令行实用工具在 SSO 中启用跟踪。</span><span class="sxs-lookup"><span data-stu-id="64920-105">Use the Trace command line utility to enable tracing in SSO.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="64920-106">Trace 命令起，文件 tracelog.exe 必须在以下目录中：</span><span class="sxs-lookup"><span data-stu-id="64920-106">For the trace command to function, the file tracelog.exe must be in the following directory:</span></span>  
>   
>  <span data-ttu-id="64920-107">\<*驱动器*\>: \Program Files\Common Files\Enterprise Single Sign-on</span><span class="sxs-lookup"><span data-stu-id="64920-107">\<*drive*\>:\Program Files\Common Files\Enterprise Single Sign-On</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="64920-108">可以从以下位置下载此文件： [http://go.microsoft.com/fwlink/?LinkId=59534](http://go.microsoft.com/fwlink/?LinkId=59534)</span><span class="sxs-lookup"><span data-stu-id="64920-108">You can download this file from the following location: [http://go.microsoft.com/fwlink/?LinkId=59534](http://go.microsoft.com/fwlink/?LinkId=59534)</span></span>  
  
#### <a name="to-use-the-trace-utility"></a><span data-ttu-id="64920-109">若要使用跟踪实用工具</span><span class="sxs-lookup"><span data-stu-id="64920-109">To use the trace utility</span></span>  
  
1.  <span data-ttu-id="64920-110">在 **“开始”** 菜单上，单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="64920-110">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="64920-111">在中**运行**对话框中，键入**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="64920-111">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="64920-112">在命令行中，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="64920-112">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="64920-113">默认值是\<驱动器\>: \Program Files\Common Files\Enterprise Single Sign-on。</span><span class="sxs-lookup"><span data-stu-id="64920-113">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="64920-114">类型**Trace – start – high**将跟踪级别设置为高并开始跟踪。</span><span class="sxs-lookup"><span data-stu-id="64920-114">Type **Trace –start –high** to set the tracing level to high and begin the trace.</span></span>  
  
5.  <span data-ttu-id="64920-115">运行方案中使用主机启动的 SSO。</span><span class="sxs-lookup"><span data-stu-id="64920-115">Run the scenario with host initiated SSO.</span></span>  
  
6.  <span data-ttu-id="64920-116">类型**Trace – 停止**以结束跟踪。</span><span class="sxs-lookup"><span data-stu-id="64920-116">Type **Trace –stop** to end the trace.</span></span> <span data-ttu-id="64920-117">在更高版本，您可以发送给 Microsoft 进行分析的目录中生成.bin 文件。</span><span class="sxs-lookup"><span data-stu-id="64920-117">A .bin file is generated in the directory above, which you can send to Microsoft for analysis.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64920-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="64920-118">See Also</span></span>  
 [<span data-ttu-id="64920-119">主机启动的 SSO</span><span class="sxs-lookup"><span data-stu-id="64920-119">Host Initiated SSO</span></span>](../core/host-initiated-sso.md)