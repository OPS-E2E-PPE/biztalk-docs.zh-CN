---
title: "如何安装 SSO 客户端实用工具 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- installing, SSO
- SSO, client utility
- client utility [SSO]
- SSO, installing
ms.assetid: e14d257e-2fde-46af-b90c-5dbc0884536b
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4eba4e0747c9566c5303e04602d957173cc56052
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-install-the-sso-client-utility"></a><span data-ttu-id="ee3ec-102">如何安装 SSO 客户端实用工具</span><span class="sxs-lookup"><span data-stu-id="ee3ec-102">How to Install the SSO Client Utility</span></span>
<span data-ttu-id="ee3ec-103">独立的 SSO 客户端实用工具 （命令行实用程序和用户的基于接口） 允许最终用户在 SSO 数据库中配置其客户端映射。</span><span class="sxs-lookup"><span data-stu-id="ee3ec-103">The stand-alone SSO client utility (command-line utility and user interface-based) allows end users to configure their client mappings in the SSO database.</span></span> <span data-ttu-id="ee3ec-104">你可以从使用 SSO 管理功能安装的自解压文件 (SSOClientInstall.exe) 安装客户端实用工具。</span><span class="sxs-lookup"><span data-stu-id="ee3ec-104">You can install the client utility from a self-extracting file (SSOClientInstall.exe) which is installed with the SSO administration feature.</span></span> <span data-ttu-id="ee3ec-105">管理员还可以安装程序包可向客户端用户通过将安装包的副本放在网络共享上。</span><span class="sxs-lookup"><span data-stu-id="ee3ec-105">Administrators can also make the installer package available to client users by placing a copy of the installer package on a network share.</span></span>  
  
 <span data-ttu-id="ee3ec-106">若要安装 SSO 客户端实用工具，你必须运行以下操作系统之一的客户端计算机上：</span><span class="sxs-lookup"><span data-stu-id="ee3ec-106">To install the SSO client utility, you must be running one of the following operating systems on the client computer:</span></span>  
  
-   [!INCLUDE[btsPlatformsComApis](../includes/btsplatformscomapis-md.md)]  
  
-   [!INCLUDE[btsDotNetFramework3.5](../includes/btsdotnetframework3-5-md.md)]<span data-ttu-id="ee3ec-107"> 或 [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)]（仅当使用基于 UI 的 SSO 客户端实用工具或利用企业 SSO 的托管互操作组件时才需要）。</span><span class="sxs-lookup"><span data-stu-id="ee3ec-107"> or [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)] (only necessary if you are using the UI-based SSO Client Utility or for leveraging the managed interoperability component of Enterprise SSO).</span></span>  
  
 <span data-ttu-id="ee3ec-108">安装后 SSO 客户端实用工具，可以启动从**启动**菜单中单击**程序**， **Microsoft Enterprise 上单一登录**，，然后**SSO 客户端实用工具**。</span><span class="sxs-lookup"><span data-stu-id="ee3ec-108">After installing the SSO Client Utility, you can launch it from the **Start** menu by clicking **Programs**, **Microsoft Enterprise Single Sign-On**, and then **SSO Client Utility**.</span></span>  
  
### <a name="to-install-the-sso-client-utility"></a><span data-ttu-id="ee3ec-109">若要安装 SSO 客户端实用工具</span><span class="sxs-lookup"><span data-stu-id="ee3ec-109">To install the SSO client utility</span></span>  
  
1.  <span data-ttu-id="ee3ec-110">双击安装程序包 SSOClientInstall。</span><span class="sxs-lookup"><span data-stu-id="ee3ec-110">Double-click the installer package SSOClientInstall.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ee3ec-111">向企业单一登录管理员索取企业中的此文件的位置。</span><span class="sxs-lookup"><span data-stu-id="ee3ec-111">Ask your Enterprise Single Sign-On Administrator for the location of this file in your enterprise.</span></span>  
  
     <span data-ttu-id="ee3ec-112">**WinZip 自动解压缩程序**程序显示。</span><span class="sxs-lookup"><span data-stu-id="ee3ec-112">The **WinZip Self-Extractor** program appears.</span></span>  
  
2.  <span data-ttu-id="ee3ec-113">选择你想要解压缩文件，然后单击的文件夹**Unzip**。</span><span class="sxs-lookup"><span data-stu-id="ee3ec-113">Select the folder where you want to unzip the files, and click **Unzip**.</span></span>  
  
     <span data-ttu-id="ee3ec-114">建议解压缩临时文件夹中的文件。</span><span class="sxs-lookup"><span data-stu-id="ee3ec-114">It is recommended to unzip the files in a temporary folder.</span></span>  
  
     <span data-ttu-id="ee3ec-115">**企业单一登录客户端安装程序**程序显示。</span><span class="sxs-lookup"><span data-stu-id="ee3ec-115">The **Enterprise Single Sign-On Client Setup** program appears.</span></span>  
  
3.  <span data-ttu-id="ee3ec-116">上**企业单一登录客户端欢迎**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="ee3ec-116">On **the Welcome to the Enterprise Single Sign-On Client** page, click **Next**.</span></span>  
  
4.  <span data-ttu-id="ee3ec-117">在许可协议页上，单击**我接受此许可协议的条款**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="ee3ec-117">On the License Agreement page, click **I accept the terms of this license agreement**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="ee3ec-118">上**用户信息**页上，键入你的用户姓名、 组织名称，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="ee3ec-118">On the **User Information** page, type your user name, organization name, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="ee3ec-119">上**开始安装**页上，单击**安装**。</span><span class="sxs-lookup"><span data-stu-id="ee3ec-119">On the **Start Installation** page, click **Install**.</span></span>  
  
7.  <span data-ttu-id="ee3ec-120">上**完成企业单一登录客户端向导**页上，单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="ee3ec-120">On the **Completing the Enterprise Single Sign-On Client Wizard** page, click **Finish**.</span></span>  
  
8.  <span data-ttu-id="ee3ec-121">指定的 SSO 服务器通过执行以下任一操作：</span><span class="sxs-lookup"><span data-stu-id="ee3ec-121">Specify the SSO server by doing either of the following:</span></span>  
  
    -   <span data-ttu-id="ee3ec-122">打开 ENTSSO 管理 MMC 管理单元中。</span><span class="sxs-lookup"><span data-stu-id="ee3ec-122">Open the ENTSSO Administration MMC Snap-In.</span></span> <span data-ttu-id="ee3ec-123">**选择 SSO 服务器**对话框将出现。</span><span class="sxs-lookup"><span data-stu-id="ee3ec-123">The **Select SSO Server** dialog will appear.</span></span> <span data-ttu-id="ee3ec-124">输入或浏览到你想要执行管理操作时，连接到 SSO 服务器。</span><span class="sxs-lookup"><span data-stu-id="ee3ec-124">Enter or browse to the SSO Server that you want to connect to when you perform administration operations.</span></span> <span data-ttu-id="ee3ec-125">若要指定计算机上的 SSO 服务器的所有用户，选择**设置 SSO 服务器的所有用户**。</span><span class="sxs-lookup"><span data-stu-id="ee3ec-125">To specify the SSO Server for all users on the machine, select **Set SSO Server for all users**.</span></span>  
  
         <span data-ttu-id="ee3ec-126">或</span><span class="sxs-lookup"><span data-stu-id="ee3ec-126">OR</span></span>  
  
    -   <span data-ttu-id="ee3ec-127">在命令提示符处，键入`ssomanage –server`指定所需的 SSO 服务器。</span><span class="sxs-lookup"><span data-stu-id="ee3ec-127">At a command prompt, type `ssomanage –server` to specify the SSO server desired.</span></span> <span data-ttu-id="ee3ec-128">您还可以键入`ssomanage -serverall`指定执行管理操作时，此计算机的所有用户将都连接到的 SSO 服务器。</span><span class="sxs-lookup"><span data-stu-id="ee3ec-128">You can also type `ssomanage -serverall` to specify the SSO server that all users of this computer will connect to when performing administration operations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee3ec-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ee3ec-129">See Also</span></span>  
 <span data-ttu-id="ee3ec-130">[如何安装 SSO 管理组件](../core/how-to-install-the-sso-administration-component.md) </span><span class="sxs-lookup"><span data-stu-id="ee3ec-130">[How to Install the SSO Administration Component](../core/how-to-install-the-sso-administration-component.md) </span></span>  
 <span data-ttu-id="ee3ec-131">[配置 SSO](../core/configuring-sso.md) </span><span class="sxs-lookup"><span data-stu-id="ee3ec-131">[Configuring SSO](../core/configuring-sso.md) </span></span>  
 [<span data-ttu-id="ee3ec-132">安装 SSO</span><span class="sxs-lookup"><span data-stu-id="ee3ec-132">Installing SSO</span></span>](../core/installing-sso.md)