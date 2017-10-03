---
title: "安装 BizTalk 适配器包 2013 R2 和 2013年 |Microsoft 文档"
description: "先决条件和步骤来安装 BAP 2013 R2 及 BizTalk Server 附带的 BAP 2013"
ms.custom: 
ms.date: 2015-12-09
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9980953a-8d38-476f-af38-4f4214ba61f2
caps.latest.revision: "107"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d91e697504adf23585392c6c761bc13b300c3ed
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="install-biztalk-adapter-pack-2013-r2-and-2013"></a><span data-ttu-id="bea0d-103">安装 BizTalk 适配器包 2013 R2 和 2013</span><span class="sxs-lookup"><span data-stu-id="bea0d-103">Install BizTalk Adapter Pack 2013 R2 and 2013</span></span>
<span data-ttu-id="bea0d-104">本文档列出的软件要求，和步骤安装 Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] (BAP) 中包含 BizTalk Server 2013 或[!INCLUDE[bts2013r2](../includes/bts2013r2-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bea0d-104">This document lists the software requirements, and the steps to install the Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] (BAP) included with BizTalk Server 2013 or [!INCLUDE[bts2013r2](../includes/bts2013r2-md.md)].</span></span>  
  
## <a name="change-log"></a><span data-ttu-id="bea0d-105">更改日志</span><span class="sxs-lookup"><span data-stu-id="bea0d-105">Change Log</span></span>  
  
|<span data-ttu-id="bea0d-106">日期</span><span class="sxs-lookup"><span data-stu-id="bea0d-106">Date</span></span>|<span data-ttu-id="bea0d-107">更改</span><span class="sxs-lookup"><span data-stu-id="bea0d-107">Change</span></span>|  
|---|---|  
|<span data-ttu-id="bea0d-108">2016 年 3 月</span><span class="sxs-lookup"><span data-stu-id="bea0d-108">March 2016</span></span>|<span data-ttu-id="bea0d-109">在**安装后...**，添加步骤来配置 Oracle 数据库适配器，以使用较新的 Oracle.DataAccess.dll 版本。</span><span class="sxs-lookup"><span data-stu-id="bea0d-109">In **After installing…**, added steps to configure Oracle Database adapter to use the newer Oracle.DataAccess.dll version.</span></span>|  
  
<a name="BKMK_Prereqs"></a>   
## <a name="software-prerequisites"></a><span data-ttu-id="bea0d-110">软件必备项</span><span class="sxs-lookup"><span data-stu-id="bea0d-110">Software prerequisites</span></span>  
 <span data-ttu-id="bea0d-111">[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]可以从使用：</span><span class="sxs-lookup"><span data-stu-id="bea0d-111">The [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] can be consumed from:</span></span>  
  
-   <span data-ttu-id="bea0d-112">.NET 应用程序</span><span class="sxs-lookup"><span data-stu-id="bea0d-112">A .NET application</span></span>  
  
-   <span data-ttu-id="bea0d-113">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bea0d-113">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span></span>  
  
-   <span data-ttu-id="bea0d-114">ADO 接口</span><span class="sxs-lookup"><span data-stu-id="bea0d-114">An ADO interface</span></span>  
  
-   <span data-ttu-id="bea0d-115">Microsoft SharePoint 门户网站</span><span class="sxs-lookup"><span data-stu-id="bea0d-115">A Microsoft SharePoint portal</span></span>  
  
 <span data-ttu-id="bea0d-116">所需的软件基于如何使用适配器，而异。</span><span class="sxs-lookup"><span data-stu-id="bea0d-116">Based on how you use the adapters, the required software varies.</span></span>  
  
### <a name="prerequisites-when-using-a-net-application"></a><span data-ttu-id="bea0d-117">使用.NET 应用程序时的先决条件</span><span class="sxs-lookup"><span data-stu-id="bea0d-117">Prerequisites when using a .NET application</span></span>  
<span data-ttu-id="bea0d-118">当使用.NET 应用程序使用的适配器，你的开发计算机 （你要在其中创建.NET 应用程序的计算机） 上需要以下软件。</span><span class="sxs-lookup"><span data-stu-id="bea0d-118">When using a .NET application to consume the adapters, the following software is required on your development computer (the computer where you're creating the .NET application).</span></span> <span data-ttu-id="bea0d-119">按列出的顺序安装软件。</span><span class="sxs-lookup"><span data-stu-id="bea0d-119">Install the software in the order listed.</span></span>
  
|<span data-ttu-id="bea0d-120">BizTalk 适配器包 2013 R2</span><span class="sxs-lookup"><span data-stu-id="bea0d-120">BizTalk Adapter Pack 2013 R2</span></span>|<span data-ttu-id="bea0d-121">BizTalk 适配器包 2013</span><span class="sxs-lookup"><span data-stu-id="bea0d-121">BizTalk Adapter Pack 2013</span></span>|  
|---|---|  
|[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]<span data-ttu-id="bea0d-122">R2， [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]，Windows 8.1、 Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="bea0d-122"> R2, [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)], Windows 8.1, Windows 7 SP1</span></span>|[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]<span data-ttu-id="bea0d-123">[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] SP1、 Windows 8、 Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="bea0d-123">, [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] SP1, Windows 8, Windows 7 SP1</span></span>|  
|[!INCLUDE[dotnet451](../includes/dotnet451-md.md)]|<span data-ttu-id="bea0d-124">Microsoft [!INCLUDE[dotnet45](../includes/dotnet45-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bea0d-124">Microsoft [!INCLUDE[dotnet45](../includes/dotnet45-md.md)]</span></span>|  
|<span data-ttu-id="bea0d-125">Visual Studio 2013</span><span class="sxs-lookup"><span data-stu-id="bea0d-125">Visual Studio 2013</span></span>|<span data-ttu-id="bea0d-126">Visual Studio 2012</span><span class="sxs-lookup"><span data-stu-id="bea0d-126">Visual Studio 2012</span></span>|  
|[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]|[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]|  
|<span data-ttu-id="bea0d-127">企业应用程序客户端和关联的软件。</span><span class="sxs-lookup"><span data-stu-id="bea0d-127">The enterprise application clients and associated software.</span></span> <span data-ttu-id="bea0d-128">请参阅[受支持的企业应用程序版本](#BKMK_SuppLOB)。</span><span class="sxs-lookup"><span data-stu-id="bea0d-128">See [Supported Enterprise Application Versions](#BKMK_SuppLOB).</span></span>|<span data-ttu-id="bea0d-129">企业应用程序客户端和关联的软件。</span><span class="sxs-lookup"><span data-stu-id="bea0d-129">The enterprise application clients and associated software.</span></span> <span data-ttu-id="bea0d-130">请参阅[受支持的企业应用程序版本](#BKMK_SuppLOB)。</span><span class="sxs-lookup"><span data-stu-id="bea0d-130">See [Supported Enterprise Application Versions](#BKMK_SuppLOB).</span></span>|  

### <a name="prerequisites-when-using-a-biztalk-server"></a><span data-ttu-id="bea0d-131">使用 BizTalk Server 时的先决条件</span><span class="sxs-lookup"><span data-stu-id="bea0d-131">Prerequisites when using a BizTalk Server</span></span>  
<span data-ttu-id="bea0d-132">当使用 BizTalk Server 使用适配器，BizTalk 服务器上需要以下软件。</span><span class="sxs-lookup"><span data-stu-id="bea0d-132">When using a BizTalk Server to consume the adapters, the following software is required on your BizTalk Server.</span></span> <span data-ttu-id="bea0d-133">按列出的顺序安装软件。</span><span class="sxs-lookup"><span data-stu-id="bea0d-133">Install the software in the order listed.</span></span>
  
|<span data-ttu-id="bea0d-134">BizTalk 适配器包 2013 R2</span><span class="sxs-lookup"><span data-stu-id="bea0d-134">BizTalk Adapter Pack 2013 R2</span></span>|<span data-ttu-id="bea0d-135">BizTalk 适配器包 2013</span><span class="sxs-lookup"><span data-stu-id="bea0d-135">BizTalk Adapter Pack 2013</span></span>|  
|---|---|  
|[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]<span data-ttu-id="bea0d-136">R2， [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]，Windows 8.1、 Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="bea0d-136"> R2, [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)], Windows 8.1, Windows 7 SP1</span></span>|[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]<span data-ttu-id="bea0d-137">[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] SP1、 Windows 8、 Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="bea0d-137">, [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] SP1, Windows 8, Windows 7 SP1</span></span>|  
|[!INCLUDE[dotnet451](../includes/dotnet451-md.md)]|<span data-ttu-id="bea0d-138">Microsoft [!INCLUDE[dotnet45](../includes/dotnet45-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bea0d-138">Microsoft [!INCLUDE[dotnet45](../includes/dotnet45-md.md)]</span></span>|  
|<span data-ttu-id="bea0d-139">Visual Studio 2013</span><span class="sxs-lookup"><span data-stu-id="bea0d-139">Visual Studio 2013</span></span>|<span data-ttu-id="bea0d-140">Visual Studio 2012</span><span class="sxs-lookup"><span data-stu-id="bea0d-140">Visual Studio 2012</span></span>|  
|[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]<br /><br /> <span data-ttu-id="bea0d-141">安装[!INCLUDE[consumeadapterservlong](../includes/consumeadapterservlong-md.md)]为[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]附带[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bea0d-141">Install the [!INCLUDE[consumeadapterservlong](../includes/consumeadapterservlong-md.md)] for [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] included with the [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].</span></span> <span data-ttu-id="bea0d-142">若要安装，请执行**自定义**(选择**BizTalk Server 外接程序**) 或**完成**安装[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bea0d-142">To install, do a **Custom** (select **BizTalk Server Addin**) or **Complete** installation of the [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].</span></span>|[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]<br /><br /> <span data-ttu-id="bea0d-143">安装[!INCLUDE[consumeadapterservlong](../includes/consumeadapterservlong-md.md)]为[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]附带[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bea0d-143">Install the [!INCLUDE[consumeadapterservlong](../includes/consumeadapterservlong-md.md)] for [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] included with the [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].</span></span> <span data-ttu-id="bea0d-144">若要安装，请执行**自定义**(选择**BizTalk Server 外接程序**) 或**完成**安装[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bea0d-144">To install, do a **Custom** (select **BizTalk Server Addin**) or **Complete** installation of the [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].</span></span>|  
|<span data-ttu-id="bea0d-145">BizTalk Server 2013 R2</span><span class="sxs-lookup"><span data-stu-id="bea0d-145">BizTalk Server 2013 R2</span></span>|<span data-ttu-id="bea0d-146">BizTalk Server 2013</span><span class="sxs-lookup"><span data-stu-id="bea0d-146">BizTalk Server 2013</span></span>|  
|<span data-ttu-id="bea0d-147">企业应用程序客户端和关联的软件。</span><span class="sxs-lookup"><span data-stu-id="bea0d-147">The enterprise application clients and associated software.</span></span> <span data-ttu-id="bea0d-148">请参阅[受支持的企业应用程序版本](#BKMK_SuppLOB)。</span><span class="sxs-lookup"><span data-stu-id="bea0d-148">See [Supported Enterprise Application Versions](#BKMK_SuppLOB).</span></span>|<span data-ttu-id="bea0d-149">企业应用程序客户端和关联的软件。</span><span class="sxs-lookup"><span data-stu-id="bea0d-149">The enterprise application clients and associated software.</span></span> <span data-ttu-id="bea0d-150">请参阅[受支持的企业应用程序版本](#BKMK_SuppLOB)。</span><span class="sxs-lookup"><span data-stu-id="bea0d-150">See [Supported Enterprise Application Versions](#BKMK_SuppLOB).</span></span>|  

### <a name="prerequisites-when-using-ado"></a><span data-ttu-id="bea0d-151">使用 ADO 时的先决条件</span><span class="sxs-lookup"><span data-stu-id="bea0d-151">Prerequisites when using ADO</span></span>  
 <span data-ttu-id="bea0d-152"> **[!INCLUDE[adaptersap](../includes/adaptersap-md.md)]** 和 **[!INCLUDE[adaptersiebel](../includes/adaptersiebel-md.md)]** 包括 ADO 层 ( *[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]* 和 *[!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]* )。</span><span class="sxs-lookup"><span data-stu-id="bea0d-152">The **[!INCLUDE[adaptersap](../includes/adaptersap-md.md)]** and **[!INCLUDE[adaptersiebel](../includes/adaptersiebel-md.md)]** include an ADO layer (*[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]* and *[!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]*).</span></span> <span data-ttu-id="bea0d-153">此 ADO 层可以用于写入的 ADO.NET 客户端可以连接到 SAP 系统或 Siebel 系统。</span><span class="sxs-lookup"><span data-stu-id="bea0d-153">This ADO layer can be used to write an ADO.NET client to connect to an SAP system or Siebel system.</span></span> <span data-ttu-id="bea0d-154">你还可用于 ADO 层与 SQL Server Integration Services (SSIS) 导入和导出数据从 LOB 应用程序和 SQL Server Reporting Services (SSRS) 生成报表来显示 LOB 系统中的数据。</span><span class="sxs-lookup"><span data-stu-id="bea0d-154">You can also use the ADO layer with SQL Server Integration Services (SSIS) to import and export data from the LOB application, and SQL Server Reporting Services (SSRS) to generate reports to present data from the LOB systems.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bea0d-155">使用 SSRS ADO 提供程序仅支持 *[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]* 。</span><span class="sxs-lookup"><span data-stu-id="bea0d-155">Using the ADO Provider with SSRS is supported only for the *[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]*.</span></span>  
  
<span data-ttu-id="bea0d-156">使用的计算机上需要以下软件[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]ADO 界面。</span><span class="sxs-lookup"><span data-stu-id="bea0d-156">The following software is required on the computer that uses the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] with an ADO interface.</span></span> <span data-ttu-id="bea0d-157">按列出的顺序安装软件。</span><span class="sxs-lookup"><span data-stu-id="bea0d-157">Install the software in the order listed.</span></span>
  
|<span data-ttu-id="bea0d-158">BizTalk 适配器包 2013 R2</span><span class="sxs-lookup"><span data-stu-id="bea0d-158">BizTalk Adapter Pack 2013 R2</span></span>|<span data-ttu-id="bea0d-159">BizTalk 适配器包 2013</span><span class="sxs-lookup"><span data-stu-id="bea0d-159">BizTalk Adapter Pack 2013</span></span>|  
|---|---|  
|[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]<span data-ttu-id="bea0d-160">R2， [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]，Windows 8.1、 Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="bea0d-160"> R2, [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)], Windows 8.1, Windows 7 SP1</span></span>|[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]<span data-ttu-id="bea0d-161">[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] SP1、 Windows 8、 Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="bea0d-161">, [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] SP1, Windows 8, Windows 7 SP1</span></span>|  
|[!INCLUDE[dotnet451](../includes/dotnet451-md.md)]|<span data-ttu-id="bea0d-162">Microsoft [!INCLUDE[dotnet45](../includes/dotnet45-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bea0d-162">Microsoft [!INCLUDE[dotnet45](../includes/dotnet45-md.md)]</span></span>|  
|<span data-ttu-id="bea0d-163">Visual Studio 2013</span><span class="sxs-lookup"><span data-stu-id="bea0d-163">Visual Studio 2013</span></span>|<span data-ttu-id="bea0d-164">Visual Studio 2012</span><span class="sxs-lookup"><span data-stu-id="bea0d-164">Visual Studio 2012</span></span>|  
|[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]|[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]|  
|[!INCLUDE[sqlserver2014](../includes/sqlserver2014-md.md)]<span data-ttu-id="bea0d-165">, [!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bea0d-165">, [!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)]</span></span>|[!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)]<span data-ttu-id="bea0d-166">, [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bea0d-166">, [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]</span></span>|  
|<span data-ttu-id="bea0d-167">企业应用程序客户端和关联的软件。</span><span class="sxs-lookup"><span data-stu-id="bea0d-167">The enterprise application clients and associated software.</span></span> <span data-ttu-id="bea0d-168">请参阅[受支持的企业应用程序版本](#BKMK_SuppLOB)。</span><span class="sxs-lookup"><span data-stu-id="bea0d-168">See [Supported Enterprise Application Versions](#BKMK_SuppLOB).</span></span>|<span data-ttu-id="bea0d-169">企业应用程序客户端和关联的软件。</span><span class="sxs-lookup"><span data-stu-id="bea0d-169">The enterprise application clients and associated software.</span></span> <span data-ttu-id="bea0d-170">请参阅[受支持的企业应用程序版本](#BKMK_SuppLOB)。</span><span class="sxs-lookup"><span data-stu-id="bea0d-170">See [Supported Enterprise Application Versions](#BKMK_SuppLOB).</span></span>|  

### <a name="prerequisites-when-using-microsoft-sharepoint"></a><span data-ttu-id="bea0d-171">使用 Microsoft SharePoint 时的先决条件</span><span class="sxs-lookup"><span data-stu-id="bea0d-171">Prerequisites when using Microsoft SharePoint</span></span>  
 <span data-ttu-id="bea0d-172">使用与 Microsoft SharePoint 的适配器的目标是在 SharePoint 门户网站上显示的 LOB 应用程序中的数据。</span><span class="sxs-lookup"><span data-stu-id="bea0d-172">The goal of using the adapters with Microsoft SharePoint is to show data from an LOB application on a SharePoint portal.</span></span>  
  
<span data-ttu-id="bea0d-173">使用典型安装[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]和 SharePoint 可以为一台计算机或为不同任务使用不同的计算机。</span><span class="sxs-lookup"><span data-stu-id="bea0d-173">A typical setup with the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] and SharePoint can be a single computer or use different computers for different tasks.</span></span> <span data-ttu-id="bea0d-174">下表总结了每个计算机的软件必备组件。</span><span class="sxs-lookup"><span data-stu-id="bea0d-174">The following table summarizes the software prerequisites for each computer.</span></span> <span data-ttu-id="bea0d-175">如果你使用的一台计算机，则会将所有软件都需要在该计算机上。</span><span class="sxs-lookup"><span data-stu-id="bea0d-175">If you are using a single computer, all the software is required on that computer.</span></span> <span data-ttu-id="bea0d-176">按列出的顺序安装软件。</span><span class="sxs-lookup"><span data-stu-id="bea0d-176">Install the software in the order listed.</span></span>  
  
|<span data-ttu-id="bea0d-177">运行 WCF 适配器服务开发向导的位置的计算机</span><span class="sxs-lookup"><span data-stu-id="bea0d-177">Computer where you run the WCF Adapter Service Development Wizard</span></span>|<span data-ttu-id="bea0d-178">其中承载 WCF 服务的计算机</span><span class="sxs-lookup"><span data-stu-id="bea0d-178">Computer where you host the WCF service</span></span>|<span data-ttu-id="bea0d-179">其中你可以使用 SharePoint 设计器来定义外部内容类型的计算机</span><span class="sxs-lookup"><span data-stu-id="bea0d-179">Computer where you can use the SharePoint Designer to define your External Content Types</span></span>|<span data-ttu-id="bea0d-180">其中使用 SharePoint 提供的 LOB 应用程序中的信息的计算机</span><span class="sxs-lookup"><span data-stu-id="bea0d-180">Computer where you use SharePoint to present the information from an LOB application</span></span>|  
|---|---|---|---|  
|<span data-ttu-id="bea0d-181">**BAP 2013 R2**:</span><span class="sxs-lookup"><span data-stu-id="bea0d-181">**BAP 2013 R2**:</span></span><ul><li>[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]<span data-ttu-id="bea0d-182"> R2</span><span class="sxs-lookup"><span data-stu-id="bea0d-182"> R2</span></span><br/>[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]<br/><span data-ttu-id="bea0d-183">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="bea0d-183">Windows 8.1</span></span><br/><span data-ttu-id="bea0d-184">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="bea0d-184">Windows 7 SP1</span></span></li><li>[!INCLUDE[dotnet451](../includes/dotnet451-md.md)]</li><li> <span data-ttu-id="bea0d-185">Visual Studio 2013</span><span class="sxs-lookup"><span data-stu-id="bea0d-185">Visual Studio 2013</span></span></li><li>[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]</li><li><span data-ttu-id="bea0d-186">Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bea0d-186">Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]</span></span></li><li><span data-ttu-id="bea0d-187">相应的企业应用程序客户端和关联的软件。</span><span class="sxs-lookup"><span data-stu-id="bea0d-187">Respective enterprise application clients and associated software.</span></span> <span data-ttu-id="bea0d-188">请参阅[受支持的企业应用程序版本](#BKMK_SuppLOB)。</span><span class="sxs-lookup"><span data-stu-id="bea0d-188">See [Supported Enterprise Application Versions](#BKMK_SuppLOB).</span></span></li></ul> <span data-ttu-id="bea0d-189">**BAP 2013**:</span><span class="sxs-lookup"><span data-stu-id="bea0d-189">**BAP 2013**:</span></span><ul><li>[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]<br/>[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]<span data-ttu-id="bea0d-190"> SP1</span><span class="sxs-lookup"><span data-stu-id="bea0d-190"> SP1</span></span><br/><span data-ttu-id="bea0d-191">Windows 8</span><span class="sxs-lookup"><span data-stu-id="bea0d-191">Windows 8</span></span><br/><span data-ttu-id="bea0d-192">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="bea0d-192">Windows 7 SP1</span></span></li><li><span data-ttu-id="bea0d-193">Microsoft [!INCLUDE[dotnet45](../includes/dotnet45-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bea0d-193">Microsoft [!INCLUDE[dotnet45](../includes/dotnet45-md.md)]</span></span></li><li><span data-ttu-id="bea0d-194">Visual Studio 2012</span><span class="sxs-lookup"><span data-stu-id="bea0d-194">Visual Studio 2012</span></span></li><li>[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]</li><li><span data-ttu-id="bea0d-195">Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bea0d-195">Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]</span></span></li><li><span data-ttu-id="bea0d-196">相应的企业应用程序客户端和关联的软件。</span><span class="sxs-lookup"><span data-stu-id="bea0d-196">Respective enterprise application clients and associated software.</span></span> <span data-ttu-id="bea0d-197">请参阅[受支持的企业应用程序版本](#BKMK_SuppLOB)。</span><span class="sxs-lookup"><span data-stu-id="bea0d-197">See [Supported Enterprise Application Versions](#BKMK_SuppLOB).</span></span></li></ul>|<span data-ttu-id="bea0d-198">**BAP 2013 R2**:</span><span class="sxs-lookup"><span data-stu-id="bea0d-198">**BAP 2013 R2**:</span></span><ul><li>[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]<span data-ttu-id="bea0d-199"> R2</span><span class="sxs-lookup"><span data-stu-id="bea0d-199"> R2</span></span><br/>[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]<br/><span data-ttu-id="bea0d-200">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="bea0d-200">Windows 8.1</span></span><br/><span data-ttu-id="bea0d-201">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="bea0d-201">Windows 7 SP1</span></span></li><li>[!INCLUDE[dotnet451](../includes/dotnet451-md.md)]</li><li>[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]</li><li><span data-ttu-id="bea0d-202">Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bea0d-202">Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]</span></span></li><li><span data-ttu-id="bea0d-203">相应的企业应用程序客户端和关联的软件。</span><span class="sxs-lookup"><span data-stu-id="bea0d-203">Respective enterprise application clients and associated software.</span></span> <span data-ttu-id="bea0d-204">请参阅[受支持的企业应用程序版本](#BKMK_SuppLOB)。</span><span class="sxs-lookup"><span data-stu-id="bea0d-204">See [Supported Enterprise Application Versions](#BKMK_SuppLOB).</span></span></li><li><span data-ttu-id="bea0d-205">附带了操作系统的 Internet 信息服务 (IIS) 版本。</span><span class="sxs-lookup"><span data-stu-id="bea0d-205">Internet Information Services (IIS) version that comes with the operating system.</span></span> <span data-ttu-id="bea0d-206">KB 224609 列出的版本。</span><span class="sxs-lookup"><span data-stu-id="bea0d-206">KB 224609 lists the versions.</span></span></li></ul><span data-ttu-id="bea0d-207">**BAP 2013**:</span><span class="sxs-lookup"><span data-stu-id="bea0d-207">**BAP 2013**:</span></span><ul><li>[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]<br/>[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]<span data-ttu-id="bea0d-208"> SP1</span><span class="sxs-lookup"><span data-stu-id="bea0d-208"> SP1</span></span><br/><span data-ttu-id="bea0d-209">Windows 8</span><span class="sxs-lookup"><span data-stu-id="bea0d-209">Windows 8</span></span><br/><span data-ttu-id="bea0d-210">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="bea0d-210">Windows 7 SP1</span></span></li><li><span data-ttu-id="bea0d-211">Microsoft [!INCLUDE[dotnet45](../includes/dotnet45-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bea0d-211">Microsoft [!INCLUDE[dotnet45](../includes/dotnet45-md.md)]</span></span></li><li>[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]</li><li><span data-ttu-id="bea0d-212">Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bea0d-212">Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]</span></span></li><li><span data-ttu-id="bea0d-213">相应的企业应用程序客户端和关联的软件。</span><span class="sxs-lookup"><span data-stu-id="bea0d-213">Respective enterprise application clients and associated software.</span></span> <span data-ttu-id="bea0d-214">请参阅[受支持的企业应用程序版本](#BKMK_SuppLOB)。</span><span class="sxs-lookup"><span data-stu-id="bea0d-214">See [Supported Enterprise Application Versions](#BKMK_SuppLOB).</span></span></li><li><span data-ttu-id="bea0d-215">附带了操作系统的 Internet 信息服务 (IIS) 版本。</span><span class="sxs-lookup"><span data-stu-id="bea0d-215">Internet Information Services (IIS) version that comes with the operating system.</span></span> <span data-ttu-id="bea0d-216">KB 224609 列出的版本。</span><span class="sxs-lookup"><span data-stu-id="bea0d-216">KB 224609 lists the versions.</span></span></li></ul>|<span data-ttu-id="bea0d-217">Microsoft Office SharePoint Server 软件开发工具包 (SDK)</span><span class="sxs-lookup"><span data-stu-id="bea0d-217">Microsoft Office SharePoint Server Software Development Kit (SDK)</span></span>|<span data-ttu-id="bea0d-218">Microsoft Office 更新服务器基础结构。</span><span class="sxs-lookup"><span data-stu-id="bea0d-218">Microsoft Office Servers Infrastructure Update.</span></span> <span data-ttu-id="bea0d-219">在下载[http://go.microsoft.com/fwlink/?LinkId=128344](http://go.microsoft.com/fwlink/?LinkId=128344)。</span><span class="sxs-lookup"><span data-stu-id="bea0d-219">Download at [http://go.microsoft.com/fwlink/?LinkId=128344](http://go.microsoft.com/fwlink/?LinkId=128344).</span></span>|  
  
<a name="BKMK_SuppLOB"></a>   
## <a name="supported-enterprise-application-versions"></a><span data-ttu-id="bea0d-220">支持的企业应用程序版本</span><span class="sxs-lookup"><span data-stu-id="bea0d-220">Supported enterprise application versions</span></span>  

<span data-ttu-id="bea0d-221">若要查看支持的特定 LOB 系统版本[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]，请参阅**[支持的业务线 (LOB) 系统](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-systems.aspx)**。</span><span class="sxs-lookup"><span data-stu-id="bea0d-221">To see the specific LOB system versions that are supported by the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)], see **[Supported Line-of-Business (LOB) systems](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-systems.aspx)**.</span></span> 

<span data-ttu-id="bea0d-222">本部分列出每个适配器，任何额外的信息，如任何客户端 Dll 所需的每个适配器。</span><span class="sxs-lookup"><span data-stu-id="bea0d-222">This section lists any extra info for each adapter, such as any client DLLs required for each adapter.</span></span>  
  
### <a name="oracle-database-adapter"></a><span data-ttu-id="bea0d-223">Oracle 数据库适配器</span><span class="sxs-lookup"><span data-stu-id="bea0d-223">Oracle Database adapter</span></span>  
  
-   <span data-ttu-id="bea0d-224">可选： 如果你使用 Oracle 数据库的分布式的事务，安装**Microsoft Transaction Server 的 Oracle 服务**（Oracle 客户端安装的一部分） 的计算机上运行适配器客户端。</span><span class="sxs-lookup"><span data-stu-id="bea0d-224">Optional: If you use distributed transactions with the Oracle database, install **Oracle Services for Microsoft Transaction Server** (part of the Oracle client installation) on the computer running the adapter client.</span></span>  
  
-   <span data-ttu-id="bea0d-225">对于你应用程序以使用 ODP.NET 的最新版本，安装**策略 Dll**并在 GAC 中注册 Dll。</span><span class="sxs-lookup"><span data-stu-id="bea0d-225">For your application to work with the most recent version of ODP.NET, install the **policy DLLs** and register the DLLs in the GAC.</span></span> <span data-ttu-id="bea0d-226">请参阅[Oracle 数据提供程序.NET 常见问题](http://www.oracle.com/technetwork/database/windows/faq-093106.html)。</span><span class="sxs-lookup"><span data-stu-id="bea0d-226">See [Oracle Data Provider for .NET FAQ](http://www.oracle.com/technetwork/database/windows/faq-093106.html).</span></span>  

### <a name="oracle-e-business-adapter"></a><span data-ttu-id="bea0d-227">Oracle E-business 适配器</span><span class="sxs-lookup"><span data-stu-id="bea0d-227">Oracle E-Business adapter</span></span>  
  
-   <span data-ttu-id="bea0d-228">可选： 若要使用 Oracle 数据库的分布式的事务，安装**Microsoft Transaction Server 的 Oracle 服务**（Oracle 客户端安装的一部分） 的计算机上运行适配器客户端。</span><span class="sxs-lookup"><span data-stu-id="bea0d-228">Optional: To use distributed transactions with the Oracle database, install **Oracle Services for Microsoft Transaction Server** (part of the Oracle client installation) on the computer running the adapter client.</span></span>  
  
-   <span data-ttu-id="bea0d-229">对于你应用程序以使用 ODP.NET 的最新版本，安装**策略 Dll**并在 GAC 中注册 Dll。</span><span class="sxs-lookup"><span data-stu-id="bea0d-229">For your application to work with the most recent version of ODP.NET, install the **policy DLLs** and register the DLLs in the GAC.</span></span> <span data-ttu-id="bea0d-230">请参阅[Oracle 数据提供程序.NET 常见问题](http://www.oracle.com/technetwork/database/windows/faq-093106.html)。</span><span class="sxs-lookup"><span data-stu-id="bea0d-230">See [Oracle Data Provider for .NET FAQ](http://www.oracle.com/technetwork/database/windows/faq-093106.html).</span></span>  
  
### <a name="sap-adapter"></a><span data-ttu-id="bea0d-231">SAP 适配器</span><span class="sxs-lookup"><span data-stu-id="bea0d-231">SAP adapter</span></span>  
  
-   <span data-ttu-id="bea0d-232">[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]需要而不考虑 SAP 系统是 Unicode 或非 Unicode 的 RFC sdk 的 Unicode 版本。</span><span class="sxs-lookup"><span data-stu-id="bea0d-232">The [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)] requires Unicode version of the RFC SDK irrespective of whether the SAP system is Unicode or non-Unicode.</span></span>  
  
-   <span data-ttu-id="bea0d-233">**所需驱动程序**： 下表列出了所需的 Dll[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]以便与 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="bea0d-233">**Required drivers**: The following table lists the DLLs required by the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] to interface with the SAP system.</span></span> <span data-ttu-id="bea0d-234">必须从 SAP 服务应用商店下载的包，包含这些 Dll 的大多数。</span><span class="sxs-lookup"><span data-stu-id="bea0d-234">Most of the packages that contain these DLLs must be downloaded from the SAP Service Marketplace.</span></span> <span data-ttu-id="bea0d-235">若要从 SAP 服务应用商店获取下载：</span><span class="sxs-lookup"><span data-stu-id="bea0d-235">To get downloads from the SAP Service Marketplace:</span></span> 
  
    1.  <span data-ttu-id="bea0d-236">从 SAP 服务应用商店安装下载管理器可用。</span><span class="sxs-lookup"><span data-stu-id="bea0d-236">Install the Download Manager available from the SAP Service Marketplace.</span></span>  
  
    2.  <span data-ttu-id="bea0d-237">通过使用你的凭据适用于 SAP 服务 Marketplace 配置下载管理器。</span><span class="sxs-lookup"><span data-stu-id="bea0d-237">Configure the Download Manager by using your credentials for the SAP Service Marketplace.</span></span>  
  
    3.  <span data-ttu-id="bea0d-238">有权通过你组织中的 SAP 管理员从 SAP 服务网站下载软件。</span><span class="sxs-lookup"><span data-stu-id="bea0d-238">Be authorized by the SAP administrator in your organization to download software from the SAP service website.</span></span> <span data-ttu-id="bea0d-239">这是必需的因为对 SAP 软件分发中心的访问权限受到下载软件授权对象。</span><span class="sxs-lookup"><span data-stu-id="bea0d-239">This is required because access to the SAP Software Distribution Center is restricted by a 'Download Software' authorization object.</span></span> <span data-ttu-id="bea0d-240">这可确保，只能由授权用户下载软件。</span><span class="sxs-lookup"><span data-stu-id="bea0d-240">This ensures that software is downloaded only by authorized users.</span></span>  
  
    4.  <span data-ttu-id="bea0d-241">安装 SAPCAR 程序，需从 SAP 服务应用商店下载的包中提取文件。</span><span class="sxs-lookup"><span data-stu-id="bea0d-241">Install the SAPCAR program, which is required to extract the files from the packages that you download from the SAP Service Marketplace.</span></span> <span data-ttu-id="bea0d-242">SAP 服务 Marketplace 也是 SAPCAR。</span><span class="sxs-lookup"><span data-stu-id="bea0d-242">SAPCAR is also available from the SAP Service Marketplace.</span></span>  
  
     <span data-ttu-id="bea0d-243">32 位和 64 位版本的[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]，必须具有相应的 32 位和 64 位版本的这些 Dll。</span><span class="sxs-lookup"><span data-stu-id="bea0d-243">For the 32-bit and 64-bit version of the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)], you must have the respective 32-bit and 64-bit versions of these DLLs.</span></span>  
  
    -   <span data-ttu-id="bea0d-244">在 32 位计算机上，必须将 Dll 的 32 位版本添加到 C:\Windows\System32 文件夹。</span><span class="sxs-lookup"><span data-stu-id="bea0d-244">On a 32-bit computer, the 32-bit version of the DLLs must be added to the C:\Windows\System32 folder.</span></span>  
  
    -   <span data-ttu-id="bea0d-245">在 64 位计算机上，必须将 Dll 的 32 位版本添加到 C:\Windows\SysWow64 文件夹。</span><span class="sxs-lookup"><span data-stu-id="bea0d-245">On a 64-bit computer, the 32-bit version of the DLLs must be added to the C:\Windows\SysWow64 folder.</span></span> <span data-ttu-id="bea0d-246">Dll 的 64 位版本必须添加到 C:\Windows\System32 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="bea0d-246">The 64-bit version of the DLLs must be added to the C:\Windows\System32 folder.</span></span>  
  
    |<span data-ttu-id="bea0d-247">SAP 客户端版本</span><span class="sxs-lookup"><span data-stu-id="bea0d-247">SAP client version</span></span>|<span data-ttu-id="bea0d-248">必需的驱动程序</span><span class="sxs-lookup"><span data-stu-id="bea0d-248">Required drivers</span></span>|  
    |------------------------|----------------------|  
    |<span data-ttu-id="bea0d-249">6.4</span><span class="sxs-lookup"><span data-stu-id="bea0d-249">6.4</span></span>|<span data-ttu-id="bea0d-250">**BizTalk 适配器包 2013年仅**</span><span class="sxs-lookup"><span data-stu-id="bea0d-250">**BizTalk Adapter Pack 2013 Only**</span></span><br /><br /> <span data-ttu-id="bea0d-251">- **SAP RFC SDK 6.40 UNICODE**。</span><span class="sxs-lookup"><span data-stu-id="bea0d-251">- **SAP RFC SDK 6.40 UNICODE**.</span></span> <span data-ttu-id="bea0d-252">这是可用的 SNOTE 一部分<sup>* </sup> 27517。若要下载 SDK 的说明进行操作都在[http://go.microsoft.com/fwlink/?LinkId=94691](http://go.microsoft.com/fwlink/?LinkId=94691)。你已下载并提取 SDK 后，将所有 Dll 从 \rfcsdk\bin 和 \rfcsdk\lib 文件夹都复制到前面此表的相关位置提到。<br /> <br /> -Dll 均可用从 SAP 作为的一部分**R3DLLINST.zip**。该文件包含 Microsoft 运行时 Dll 并可以从 SAP 站点下载。请参阅 SNOTE<sup> * </sup> 684106 有关详细信息。</span><span class="sxs-lookup"><span data-stu-id="bea0d-252">This is available as part of SNOTE<sup>*</sup> 27517. The instructions to download the SDK are available at [http://go.microsoft.com/fwlink/?LinkId=94691](http://go.microsoft.com/fwlink/?LinkId=94691). After you have downloaded and extracted the SDK, copy all the DLLs from the \rfcsdk\bin and \rfcsdk\lib folders to the relevant location mentioned preceding this table.<br /><br /> - DLLs are available from SAP as part of **R3DLLINST.zip**. This contains Microsoft run-time DLLs and can be downloaded from the SAP site. See SNOTE<sup>*</sup> 684106 for more information.</span></span> <span data-ttu-id="bea0d-253">你可以下载的.zip 文件[http://go.microsoft.com/fwlink/?LinkId=94693](http://go.microsoft.com/fwlink/?LinkId=94693)。</span><span class="sxs-lookup"><span data-stu-id="bea0d-253">You can download the .zip file from [http://go.microsoft.com/fwlink/?LinkId=94693](http://go.microsoft.com/fwlink/?LinkId=94693).</span></span> <span data-ttu-id="bea0d-254">此链接已从你可以在其中下载包"附件"选项。</span><span class="sxs-lookup"><span data-stu-id="bea0d-254">This link has an “Attachments” option from where you can download the package.</span></span><br /><br /> <span data-ttu-id="bea0d-255">-如果你使用 SAP 安全网络通信 (SNC) 连接到 SAP 系统，你还必须从 SAP 相关的 Dll。</span><span class="sxs-lookup"><span data-stu-id="bea0d-255">- If you use SAP Secure Network Communications (SNC) to connect to an SAP system, you must also have the relevant DLLs from SAP.</span></span> <span data-ttu-id="bea0d-256">这些 Dll 是不同的 32 位和 64 位平台且可提供与 SNOTE<sup> * </sup> 352295。</span><span class="sxs-lookup"><span data-stu-id="bea0d-256">These DLLs are different for 32-bit and 64-bit platforms and are available with SNOTE<sup>*</sup> 352295.</span></span> <span data-ttu-id="bea0d-257">你可以下载从 Dll [http://go.microsoft.com/fwlink/?LinkId=104032](http://go.microsoft.com/fwlink/?LinkId=104032)。</span><span class="sxs-lookup"><span data-stu-id="bea0d-257">You can download the DLLs from [http://go.microsoft.com/fwlink/?LinkId=104032](http://go.microsoft.com/fwlink/?LinkId=104032).</span></span> <span data-ttu-id="bea0d-258">此链接已从你可以在其中下载包"附件"选项。</span><span class="sxs-lookup"><span data-stu-id="bea0d-258">This link has an “Attachments” option from where you can download the package.</span></span> <span data-ttu-id="bea0d-259">Dll 的名称为：</span><span class="sxs-lookup"><span data-stu-id="bea0d-259">The names of the DLLs are:</span></span><br /><br /> <span data-ttu-id="bea0d-260">- **适用于 32 位**: gsskrb5.dll、 gssntlm.dll</span><span class="sxs-lookup"><span data-stu-id="bea0d-260">- **For 32-bit**: gsskrb5.dll, gssntlm.dll</span></span><br /><br /> <span data-ttu-id="bea0d-261">-  **为 64 位 x86**: gx64krb5.dll、 gx64ntlm.dll</span><span class="sxs-lookup"><span data-stu-id="bea0d-261">-  **For 64-bit x86**: gx64krb5.dll, gx64ntlm.dll</span></span>|  
    |<span data-ttu-id="bea0d-262">7.0</span><span class="sxs-lookup"><span data-stu-id="bea0d-262">7.0</span></span>|<span data-ttu-id="bea0d-263">- **SAP RFC SDK 7.00 UNICODE**。</span><span class="sxs-lookup"><span data-stu-id="bea0d-263">- **SAP RFC SDK 7.00 UNICODE**.</span></span> <span data-ttu-id="bea0d-264">这是可用的 SNOTE 一部分<sup>* </sup> 27517。若要下载 SDK 的说明进行操作都在[http://go.microsoft.com/fwlink/?LinkId=94691](http://go.microsoft.com/fwlink/?LinkId=94691)。你已下载并提取 SDK 后，将复制所有 Dll，从 \rfcsdk\bin 和 \rfcsdk\lib 文件夹和前面此表的相关位置提到。<br /> <br /> -Dll 均可用从 SAP 作为的一部分**R3DLLINST.zip**。该文件包含 Microsoft 运行时 Dll 并可以从 SAP 站点下载。请参阅 SNOTE<sup> * </sup> 684106 有关详细信息。</span><span class="sxs-lookup"><span data-stu-id="bea0d-264">This is available as part of SNOTE<sup>*</sup> 27517. The instructions to download the SDK are available at [http://go.microsoft.com/fwlink/?LinkId=94691](http://go.microsoft.com/fwlink/?LinkId=94691). After you have downloaded and extracted the SDK, copy all the DLLs from the \rfcsdk\bin and \rfcsdk\lib folders and to the relevant location mentioned preceding this table.<br /><br /> - DLLs are available from SAP as part of **R3DLLINST.zip**. This contains Microsoft run-time DLLs and can be downloaded from the SAP site. See SNOTE<sup>*</sup> 684106 for more information.</span></span> <span data-ttu-id="bea0d-265">你可以下载的.zip 文件[http://go.microsoft.com/fwlink/?LinkId=94693](http://go.microsoft.com/fwlink/?LinkId=94693)。</span><span class="sxs-lookup"><span data-stu-id="bea0d-265">You can download the .zip file from [http://go.microsoft.com/fwlink/?LinkId=94693](http://go.microsoft.com/fwlink/?LinkId=94693).</span></span> <span data-ttu-id="bea0d-266">此链接已从你可以在其中下载包"附件"选项。</span><span class="sxs-lookup"><span data-stu-id="bea0d-266">This link has an “Attachments” option from where you can download the package.</span></span><br /><br /> <span data-ttu-id="bea0d-267">-如果你使用 SAP 安全网络通信 (SNC) 连接到 SAP 系统，你还必须从 SAP 相关的 Dll。</span><span class="sxs-lookup"><span data-stu-id="bea0d-267">- If you use SAP Secure Network Communications (SNC) to connect to an SAP system, you must also have the relevant DLLs from SAP.</span></span> <span data-ttu-id="bea0d-268">这些 Dll 是不同的 32 位和 64 位平台且可提供与 SNOTE<sup> * </sup> 352295。</span><span class="sxs-lookup"><span data-stu-id="bea0d-268">These DLLs are different for 32-bit and 64-bit platforms and are available with SNOTE<sup>*</sup> 352295.</span></span> <span data-ttu-id="bea0d-269">你可以下载从 Dll [http://go.microsoft.com/fwlink/?LinkId=104032](http://go.microsoft.com/fwlink/?LinkId=104032)。</span><span class="sxs-lookup"><span data-stu-id="bea0d-269">You can download the DLLs from [http://go.microsoft.com/fwlink/?LinkId=104032](http://go.microsoft.com/fwlink/?LinkId=104032).</span></span> <span data-ttu-id="bea0d-270">此链接已从你可以在其中下载包"附件"选项。</span><span class="sxs-lookup"><span data-stu-id="bea0d-270">This link has an “Attachments” option from where you can download the package.</span></span> <span data-ttu-id="bea0d-271">Dll 的名称为：</span><span class="sxs-lookup"><span data-stu-id="bea0d-271">The names of the DLLs are:</span></span><br /><br /> <span data-ttu-id="bea0d-272">- **适用于 32 位**: gsskrb5.dll、 gssntlm.dll</span><span class="sxs-lookup"><span data-stu-id="bea0d-272">- **For 32-bit**: gsskrb5.dll, gssntlm.dll</span></span><br /><br /> <span data-ttu-id="bea0d-273">- **为 64 位 x86**: gx64krb5.dll、 gx64ntlm.dll</span><span class="sxs-lookup"><span data-stu-id="bea0d-273">- **For 64-bit x86**: gx64krb5.dll, gx64ntlm.dll</span></span>|  
    |<span data-ttu-id="bea0d-274">7.1</span><span class="sxs-lookup"><span data-stu-id="bea0d-274">7.1</span></span>|<span data-ttu-id="bea0d-275">- **SAP RFC SDK 7.10 UNICODE**。</span><span class="sxs-lookup"><span data-stu-id="bea0d-275">- **SAP RFC SDK 7.10 UNICODE**.</span></span> <span data-ttu-id="bea0d-276">这是可用的 SNOTE 一部分<sup>* </sup> 27517。若要下载 SDK 的说明进行操作都在[http://go.microsoft.com/fwlink/?LinkId=94691](http://go.microsoft.com/fwlink/?LinkId=94691)。你已下载并提取 SDK 后，将所有 Dll 从 \rfcsdk\bin 和 \rfcsdk\lib 文件夹都复制到前面此表的相关位置提到。<br /> <br /> -Dll 均可用从 SAP 作为的一部分**R3DLLINST.zip**。该文件包含 Microsoft 运行时 Dll 并可以从 SAP 站点下载。请参阅 SNOTE<sup> * </sup> 684106 有关详细信息。</span><span class="sxs-lookup"><span data-stu-id="bea0d-276">This is available as part of SNOTE<sup>*</sup> 27517. The instructions to download the SDK are available at [http://go.microsoft.com/fwlink/?LinkId=94691](http://go.microsoft.com/fwlink/?LinkId=94691). After you have downloaded and extracted the SDK, copy all the DLLs from the \rfcsdk\bin and \rfcsdk\lib folders to the relevant location mentioned preceding this table.<br /><br /> - DLLs are available from SAP as part of **R3DLLINST.zip**. This contains Microsoft run-time DLLs and can be downloaded from the SAP site. See SNOTE<sup>*</sup> 684106 for more information.</span></span> <span data-ttu-id="bea0d-277">你可以下载的.zip 文件[http://go.microsoft.com/fwlink/?LinkId=94693](http://go.microsoft.com/fwlink/?LinkId=94693)。</span><span class="sxs-lookup"><span data-stu-id="bea0d-277">You can download the .zip file from [http://go.microsoft.com/fwlink/?LinkId=94693](http://go.microsoft.com/fwlink/?LinkId=94693).</span></span> <span data-ttu-id="bea0d-278">此链接已从你可以在其中下载包"附件"选项。</span><span class="sxs-lookup"><span data-stu-id="bea0d-278">This link has an “Attachments” option from where you can download the package.</span></span><br /><br /> <span data-ttu-id="bea0d-279">Microsoft Visual c + + 运行时 Dll 所需的 SAP 7.1 客户端是可从以下链接：</span><span class="sxs-lookup"><span data-stu-id="bea0d-279">- Microsoft Visual C++ run-time DLLs required for SAP 7.1 client are available from the following links:</span></span><br /><br /> <span data-ttu-id="bea0d-280">- **32 位 SAP 7.1 客户端**： 从 Vcredist_x86.exe [http://go.microsoft.com/fwlink/?LinkId=107086](http://go.microsoft.com/fwlink/?LinkId=107086)。</span><span class="sxs-lookup"><span data-stu-id="bea0d-280">- **For 32-bit SAP 7.1 client**:  Vcredist_x86.exe from [http://go.microsoft.com/fwlink/?LinkId=107086](http://go.microsoft.com/fwlink/?LinkId=107086).</span></span><br /><br /> <span data-ttu-id="bea0d-281">-                                 **64 位 SAP 7.1 客户端**： 从 Vcredist_x64.exe [http://go.microsoft.com/fwlink/?LinkId=107087](http://go.microsoft.com/fwlink/?LinkId=107087)。</span><span class="sxs-lookup"><span data-stu-id="bea0d-281">-                                 **For 64-bit SAP 7.1 client**: Vcredist_x64.exe from [http://go.microsoft.com/fwlink/?LinkId=107087](http://go.microsoft.com/fwlink/?LinkId=107087).</span></span><br /><br /> <span data-ttu-id="bea0d-282">-如果你使用 SAP 安全网络通信 (SNC) 连接到 SAP 系统，你还必须从 SAP 相关的 Dll。</span><span class="sxs-lookup"><span data-stu-id="bea0d-282">- If you use SAP Secure Network Communications (SNC) to connect to an SAP system, you must also have the relevant DLLs from SAP.</span></span> <span data-ttu-id="bea0d-283">这些 Dll 是不同的 32 位和 64 位平台且可提供与 SNOTE<sup> * </sup> 352295。</span><span class="sxs-lookup"><span data-stu-id="bea0d-283">These DLLs are different for 32-bit and 64-bit platforms and are available with SNOTE<sup>*</sup> 352295.</span></span> <span data-ttu-id="bea0d-284">你可以下载从 Dll [http://go.microsoft.com/fwlink/?LinkId=104032](http://go.microsoft.com/fwlink/?LinkId=104032)。</span><span class="sxs-lookup"><span data-stu-id="bea0d-284">You can download the DLLs from [http://go.microsoft.com/fwlink/?LinkId=104032](http://go.microsoft.com/fwlink/?LinkId=104032).</span></span> <span data-ttu-id="bea0d-285">此链接已从你可以在其中下载包"附件"选项。</span><span class="sxs-lookup"><span data-stu-id="bea0d-285">This link has an “Attachments” option from where you can download the package.</span></span> <span data-ttu-id="bea0d-286">Dll 的名称为：</span><span class="sxs-lookup"><span data-stu-id="bea0d-286">The names of the DLLs are:</span></span><br /><br /> <span data-ttu-id="bea0d-287">- **适用于 32 位**: gsskrb5.dll、 gssntlm.dll</span><span class="sxs-lookup"><span data-stu-id="bea0d-287">- **For 32-bit**: gsskrb5.dll, gssntlm.dll</span></span><br /><br /> <span data-ttu-id="bea0d-288">- **为 64 位 x86**: gx64krb5.dll、 gx64ntlm.dll</span><span class="sxs-lookup"><span data-stu-id="bea0d-288">- **For 64-bit x86**: gx64krb5.dll, gx64ntlm.dll</span></span>|  
  
     * <span data-ttu-id="bea0d-289">SNOTEs 是伴随发布 sap 修复程序的发行说明。</span><span class="sxs-lookup"><span data-stu-id="bea0d-289">SNOTEs are release notes that accompany fixes released by SAP.</span></span>  

### <a name="siebel-adapter"></a><span data-ttu-id="bea0d-290">Siebel 适配器</span><span class="sxs-lookup"><span data-stu-id="bea0d-290">Siebel adapter</span></span>  
<span data-ttu-id="bea0d-291">任何额外的步骤。</span><span class="sxs-lookup"><span data-stu-id="bea0d-291">No extra steps.</span></span>
  
### <a name="sql-adapter"></a><span data-ttu-id="bea0d-292">SQL 适配器</span><span class="sxs-lookup"><span data-stu-id="bea0d-292">SQL adapter</span></span>  
  
<span data-ttu-id="bea0d-293">**所需驱动程序**:</span><span class="sxs-lookup"><span data-stu-id="bea0d-293">**Required drivers**:</span></span>  
  
-   <span data-ttu-id="bea0d-294">**为 SQL Server 2005**： 如果在 SQL Server 中创建用户定义类型 (Udt)，请确保 Udt 的相应程序集添加到 GAC。</span><span class="sxs-lookup"><span data-stu-id="bea0d-294">**For SQL Server 2005**: If you create User Defined Types (UDTs) in SQL Server, make sure the respective assemblies for the UDTs are added to the GAC.</span></span>  
  
-   <span data-ttu-id="bea0d-295">**SQL server 2014，SQL Server 2012，SQL Server 2008 R2、 SQL Server 2008 SP1**:</span><span class="sxs-lookup"><span data-stu-id="bea0d-295">**For SQL Server 2014, SQL Server 2012, SQL Server 2008 R2,SQL Server 2008 SP1**:</span></span>  
  
    -   <span data-ttu-id="bea0d-296">如果你使用随 SQL Server 版本，例如，Geography，Udt 请确保以下 Dll 计算机上存在其中你使用该适配器在 SQL Server 上执行操作。</span><span class="sxs-lookup"><span data-stu-id="bea0d-296">If you use the UDTs shipped with the SQL Server versions, for example, Geography, make sure the following DLLs are present on the computer where you use the adapter to perform operations on SQL Server.</span></span> <span data-ttu-id="bea0d-297">例如，如果你创建 BizTalk 项目，在 SQL Server 上执行操作，这些 Dll 必须存在于运行 BizTalk Server 的计算机上。</span><span class="sxs-lookup"><span data-stu-id="bea0d-297">For example, if you create BizTalk projects to perform operations on SQL Server, these DLLs must be present on the computer where BizTalk Server is running.</span></span>  
  
        -   <span data-ttu-id="bea0d-298">请确保 Microsoft.SqlServer.Types.dll 已添加到 GAC。</span><span class="sxs-lookup"><span data-stu-id="bea0d-298">Make sure Microsoft.SqlServer.Types.dll is added to the GAC.</span></span>  
  
        -   <span data-ttu-id="bea0d-299">确保 SqlServerSpatial.dll System32 文件夹中可用。</span><span class="sxs-lookup"><span data-stu-id="bea0d-299">Make sure SqlServerSpatial.dll is available in the System32 folder.</span></span>    
        
        <span data-ttu-id="bea0d-300">可以通过运行 SQL Server 安装程序并选择在计算机上安装这些 Dll**管理工具-基本**和**管理工具 – 完整**中**功能选择**向导页。</span><span class="sxs-lookup"><span data-stu-id="bea0d-300">You can install these DLLs on the computer by running the SQL Server setup and selecting **Management Tools – Basic** and **Management Tools – Complete** in the **Feature Selection** page of the wizard.</span></span>          
  
    -   <span data-ttu-id="bea0d-301">如果你使用该适配器上的 FILESTREAM 数据类型的列执行操作，请确保已安装的 SQL 客户端连接 SDK。</span><span class="sxs-lookup"><span data-stu-id="bea0d-301">If you use the adapter to perform operations on columns of FILESTREAM data types, make sure you have SQL Client Connectivity SDK installed.</span></span> <span data-ttu-id="bea0d-302">你可以通过运行 SQL Server 安装程序并选择安装 SQL 客户端连接 SDK **SQL 客户端连接 SDK**中**功能选择**向导页。</span><span class="sxs-lookup"><span data-stu-id="bea0d-302">You can install the SQL Client Connectivity SDK by running the SQL Server setup and selecting **SQL Client Connectivity SDK** in the **Feature Selection** page of the wizard.</span></span> <span data-ttu-id="bea0d-303">适配器使用 sqlncli10.dll，安装 SQL 客户端连接 SDK，与执行 FILESTREAM 操作。</span><span class="sxs-lookup"><span data-stu-id="bea0d-303">The adapter uses the sqlncli10.dll, installed with the SQL Client Connectivity SDK, to perform FILESTREAM operations.</span></span>  

    -   <span data-ttu-id="bea0d-304">如果在 SQL Server 中创建你自己的 Udt，请确保 Udt 的相应程序集添加到 GAC。</span><span class="sxs-lookup"><span data-stu-id="bea0d-304">If you create your own UDTs in SQL Server, make sure the respective assemblies for the UDTs are added to the GAC.</span></span>

## <a name="64-bit-support"></a><span data-ttu-id="bea0d-305">64 位支持</span><span class="sxs-lookup"><span data-stu-id="bea0d-305">64-bit support</span></span>

<span data-ttu-id="bea0d-306">Siebel 适配器被支持在 32 位主机实例中。</span><span class="sxs-lookup"><span data-stu-id="bea0d-306">The Siebel adapter is supported in a 32-bit host instance.</span></span> <span data-ttu-id="bea0d-307">它不被支持的 64 位主机实例中运行 Siebel 适配器。</span><span class="sxs-lookup"><span data-stu-id="bea0d-307">It is not supported to run the Siebel adapter in a 64-bit host instance.</span></span> 

<span data-ttu-id="bea0d-308">所有其他适配器可以在一个 32 位或 64 位主机实例中运行。</span><span class="sxs-lookup"><span data-stu-id="bea0d-308">All the other adapters can run in a 32-bit or 64-bit host instance.</span></span> 


  
 <span data-ttu-id="bea0d-309">有关安装的 32 位和 64 位的受支持的安装方案的详细信息[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]，请参阅[在 32 位和 64 位平台上安装 BizTalk 适配器包方案](#BKMK_Install_Scenarios)。</span><span class="sxs-lookup"><span data-stu-id="bea0d-309">For more information about the supported installation scenarios for installing the 32-bit and 64-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)], see [Scenarios for Installing the BizTalk Adapter Pack on 32-bit and 64-bit Platforms](#BKMK_Install_Scenarios).</span></span>  
  
<a name="BKMK_Install_Adap"></a>   
## <a name="installing-the-biztalk-adapter-pack"></a><span data-ttu-id="bea0d-310">安装 BizTalk 适配器包</span><span class="sxs-lookup"><span data-stu-id="bea0d-310">Installing the BizTalk Adapter Pack</span></span>  
 <span data-ttu-id="bea0d-311">确保所有[软件必备项](#BKMK_Prereqs)在安装之前安装[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bea0d-311">Make sure all the [software prerequisites](#BKMK_Prereqs) are installed before installing the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="bea0d-312">你可以安装[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]以下两种方式：</span><span class="sxs-lookup"><span data-stu-id="bea0d-312">You can install the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] in the following two ways:</span></span>  
  
-   <span data-ttu-id="bea0d-313">**在交互模式中**： 运行安装程序向导</span><span class="sxs-lookup"><span data-stu-id="bea0d-313">**In interactive mode**: Run the setup wizard</span></span>  
  
-   <span data-ttu-id="bea0d-314">**在静默模式下**： 使用命令行</span><span class="sxs-lookup"><span data-stu-id="bea0d-314">**In silent mode**: Use the command line</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="bea0d-315">必须在其中安装的计算机上具有管理特权[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]，不管是否使用安装向导或命令行。</span><span class="sxs-lookup"><span data-stu-id="bea0d-315">You must have administrative privileges on the computer where you install the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)], irrespective of whether you are installing using the wizard or the command line.</span></span>  

### <a name="typical-vs-custom-installation"></a><span data-ttu-id="bea0d-316">典型安装与自定义安装</span><span class="sxs-lookup"><span data-stu-id="bea0d-316">Typical vs custom installation</span></span>  
<span data-ttu-id="bea0d-317">本部分列出的安装类型，以及每个选项安装的功能：</span><span class="sxs-lookup"><span data-stu-id="bea0d-317">This section lists the installation types, and the features that are installed with each option:</span></span>  
  
-   <span data-ttu-id="bea0d-318">**典型**和**完成**选项安装所有的适配器，请与关联的数据提供程序。</span><span class="sxs-lookup"><span data-stu-id="bea0d-318">The **Typical** and **Complete** options install all the adapters, with the associated data providers.</span></span> <span data-ttu-id="bea0d-319">你没有选择特定的适配器的安装的选项。</span><span class="sxs-lookup"><span data-stu-id="bea0d-319">You do not have the option of choosing a specific adapter to install.</span></span>  
  
-   <span data-ttu-id="bea0d-320">**自定义**选项与关联的数据提供程序安装一个或多个适配器。</span><span class="sxs-lookup"><span data-stu-id="bea0d-320">The **Custom** option installs one or more adapters, with the associated data providers.</span></span> <span data-ttu-id="bea0d-321">你可以选择要安装哪些适配器。</span><span class="sxs-lookup"><span data-stu-id="bea0d-321">You can choose which adapters to install.</span></span> <span data-ttu-id="bea0d-322">如果你选择安装数据提供程序，你还必须安装相应的适配器。</span><span class="sxs-lookup"><span data-stu-id="bea0d-322">If you choose to install a data provider, you must also install the corresponding adapter.</span></span> <span data-ttu-id="bea0d-323">但是，你可以安装适配器，而无需安装相应的数据提供程序。</span><span class="sxs-lookup"><span data-stu-id="bea0d-323">However, you can install an adapter without installing the corresponding data provider.</span></span> <span data-ttu-id="bea0d-324">执行此操作通过展开**ADO 提供程序**节点，，然后选择你不想要安装的提供程序。</span><span class="sxs-lookup"><span data-stu-id="bea0d-324">Do this by expanding the **ADO Providers** node, and then selecting the providers that you don't want to install.</span></span> <span data-ttu-id="bea0d-325">请参阅[在交互模式中安装 BizTalk 适配器包](#BKMK_Install_wizard)。</span><span class="sxs-lookup"><span data-stu-id="bea0d-325">See [Installing the BizTalk Adapter Pack in Interactive Mode](#BKMK_Install_wizard).</span></span>  
  
     <span data-ttu-id="bea0d-326">例如，如果你安装[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]，还必须安装[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bea0d-326">For example, if you install the [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)], you must also install the [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="bea0d-327">但是，你可以安装[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]而无需安装[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bea0d-327">However, you can install the [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)] without installing the [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)].</span></span>  
  
<a name="BKMK_Install_Scenarios"></a>   
### <a name="scenarios-for-installing-the-biztalk-adapter-pack-on-32-bit-and-64-bit-platforms"></a><span data-ttu-id="bea0d-328">在 32 位和 64 位平台上安装 BizTalk 适配器包方案</span><span class="sxs-lookup"><span data-stu-id="bea0d-328">Scenarios for installing the BizTalk Adapter Pack on 32-bit and 64-bit platforms</span></span>  
 <span data-ttu-id="bea0d-329">与[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]可用于：</span><span class="sxs-lookup"><span data-stu-id="bea0d-329">With [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] can be used for:</span></span> 
  
-   [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]<span data-ttu-id="bea0d-330">设计时 （在生成 LOB 应用程序上的操作的元数据）</span><span class="sxs-lookup"><span data-stu-id="bea0d-330"> design time (when generating metadata for operations on LOB applications)</span></span>
  
-   <span data-ttu-id="bea0d-331">BizTalk Server 管理控制台 （用于创建的物理端口） 的设计时</span><span class="sxs-lookup"><span data-stu-id="bea0d-331">BizTalk Server Administration console design time (for creating physical ports)</span></span>
  
    > [!NOTE]
    >  <span data-ttu-id="bea0d-332">BizTalk Server 管理控制台将作为 32 位 Microsoft 管理控制台 (MMC) 应用程序运行。</span><span class="sxs-lookup"><span data-stu-id="bea0d-332">BizTalk Server Administration console runs as a 32-bit Microsoft Management Console (MMC) application.</span></span>  
  
-   <span data-ttu-id="bea0d-333">BizTalk 运行时 （发送和接收消息时从 LOB 应用程序）</span><span class="sxs-lookup"><span data-stu-id="bea0d-333">BizTalk run time (when sending and receiving messages from LOB applications)</span></span>

<span data-ttu-id="bea0d-334">你可以为所有这些大小，使用一台计算机，或使用不同的计算机。</span><span class="sxs-lookup"><span data-stu-id="bea0d-334">You can use a single computer for all these taks, or use different computers.</span></span> <span data-ttu-id="bea0d-335">因为同时[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]和 BizTalk MMC 是 32 位进程，则必须安装 32 位[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]你在其中完成的设计时任务的计算机上。</span><span class="sxs-lookup"><span data-stu-id="bea0d-335">Because both [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] and BizTalk MMC are 32-bit processes, you must install the 32-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] on the computer where you complete the design-time tasks.</span></span> 

#### <a name="scenarios-for-installing-the-biztalk-adapter-pack-on-a-32-bit-platform"></a><span data-ttu-id="bea0d-336">在 32 位平台上安装 BizTalk 适配器包方案</span><span class="sxs-lookup"><span data-stu-id="bea0d-336">Scenarios for installing the BizTalk Adapter Pack on a 32-bit platform</span></span>  
 <span data-ttu-id="bea0d-337">在 32 位平台上支持的方案包括：</span><span class="sxs-lookup"><span data-stu-id="bea0d-337">The supported scenarios on a 32-bit platform include:</span></span>  
  
|<span data-ttu-id="bea0d-338">为 Visual Studio 设计时</span><span class="sxs-lookup"><span data-stu-id="bea0d-338">For Visual Studio design time</span></span>|<span data-ttu-id="bea0d-339">为 BizTalk MMC 设计时</span><span class="sxs-lookup"><span data-stu-id="bea0d-339">For BizTalk MMC design time</span></span>|<span data-ttu-id="bea0d-340">有关 BizTalk 运行时</span><span class="sxs-lookup"><span data-stu-id="bea0d-340">For BizTalk run time</span></span>|<span data-ttu-id="bea0d-341">Visual Studio 设计时间和/或 BizTalk MMC 设计时 + BizTalk 运行时</span><span class="sxs-lookup"><span data-stu-id="bea0d-341">For Visual Studio design time and/or BizTalk MMC design time + BizTalk run time</span></span>|  
|---|---|---|---|  
|<span data-ttu-id="bea0d-342">-安装 32 位[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bea0d-342">- Install 32-bit [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="bea0d-343">-安装 32 位[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bea0d-343">- Install 32-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="bea0d-344">-安装 32 位 LOB 客户端和其他必要的 Dll。</span><span class="sxs-lookup"><span data-stu-id="bea0d-344">- Install 32-bit LOB client and other required DLLs.</span></span>|<span data-ttu-id="bea0d-345">-安装 32 位[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bea0d-345">- Install 32-bit [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="bea0d-346">-安装 32 位[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bea0d-346">- Install 32-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="bea0d-347">-安装 32 位 LOB 客户端和其他必要的 Dll。</span><span class="sxs-lookup"><span data-stu-id="bea0d-347">- Install 32-bit LOB client and other required DLLs.</span></span>|<span data-ttu-id="bea0d-348">-安装 32 位[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bea0d-348">- Install 32-bit [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="bea0d-349">-安装 32 位[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bea0d-349">- Install 32-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="bea0d-350">-安装 32 位 LOB 客户端和其他必要的 Dll。</span><span class="sxs-lookup"><span data-stu-id="bea0d-350">- Install 32-bit LOB client and other required DLLs.</span></span>|<span data-ttu-id="bea0d-351">-安装 32 位[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bea0d-351">- Install 32-bit [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="bea0d-352">-安装 32 位[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bea0d-352">- Install 32-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="bea0d-353">-安装 32 位 LOB 客户端和其他必要的 Dll。</span><span class="sxs-lookup"><span data-stu-id="bea0d-353">- Install 32-bit LOB client and other required DLLs.</span></span>|  
  
#### <a name="scenarios-for-installing-the-biztalk-adapter-pack-on-a-64-bit-platform"></a><span data-ttu-id="bea0d-354">在 64 位平台上安装 BizTalk 适配器包方案</span><span class="sxs-lookup"><span data-stu-id="bea0d-354">Scenarios for installing the BizTalk Adapter Pack on a 64-bit platform</span></span>  
 <span data-ttu-id="bea0d-355">在 64 位平台上支持的方案包括：</span><span class="sxs-lookup"><span data-stu-id="bea0d-355">The supported scenarios on a 64-bit platform include:</span></span>  
  
|<span data-ttu-id="bea0d-356">为 Visual Studio 设计时</span><span class="sxs-lookup"><span data-stu-id="bea0d-356">For Visual Studio design time</span></span>|<span data-ttu-id="bea0d-357">为 BizTalk MMC 设计时</span><span class="sxs-lookup"><span data-stu-id="bea0d-357">For BizTalk MMC design time</span></span>|<span data-ttu-id="bea0d-358">有关 BizTalk 运行时</span><span class="sxs-lookup"><span data-stu-id="bea0d-358">For BizTalk run time</span></span>|<span data-ttu-id="bea0d-359">Visual Studio 设计时间和/或 BizTalk MMC 设计时 + BizTalk 运行时</span><span class="sxs-lookup"><span data-stu-id="bea0d-359">For Visual Studio design time and/or BizTalk MMC design time + BizTalk run time</span></span>|  
|---|---|---|---|  
|<span data-ttu-id="bea0d-360">-安装 64 位[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bea0d-360">- Install 64-bit [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="bea0d-361">-安装 32 位[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bea0d-361">- Install 32-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="bea0d-362">-安装 32 位 LOB 客户端和其他必要的 Dll。</span><span class="sxs-lookup"><span data-stu-id="bea0d-362">- Install 32-bit LOB client and other required DLLs.</span></span>|<span data-ttu-id="bea0d-363">-安装 64 位[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bea0d-363">- Install 64-bit [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="bea0d-364">-安装 32 位[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bea0d-364">- Install 32-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="bea0d-365">-安装 32 位 LOB 客户端和其他必要的 Dll。</span><span class="sxs-lookup"><span data-stu-id="bea0d-365">- Install 32-bit LOB client and other required DLLs.</span></span>|<span data-ttu-id="bea0d-366">**对于 32 位 BizTalk 进程**:</span><span class="sxs-lookup"><span data-stu-id="bea0d-366">**For a 32-bit BizTalk process**:</span></span><br /><br /> <span data-ttu-id="bea0d-367">-安装 64 位[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bea0d-367">- Install 64-bit [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="bea0d-368">-安装 32 位[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bea0d-368">- Install 32-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="bea0d-369">-安装 32 位 LOB 客户端和其他必要的 Dll。</span><span class="sxs-lookup"><span data-stu-id="bea0d-369">- Install 32-bit LOB client and other required DLLs.</span></span><br /><br /> <span data-ttu-id="bea0d-370">**对于 64 位 BizTalk 进程**:</span><span class="sxs-lookup"><span data-stu-id="bea0d-370">**For a 64-bit BizTalk process**:</span></span><br /><br /> <span data-ttu-id="bea0d-371">-安装 64 位[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bea0d-371">- Install 64-bit [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="bea0d-372">-安装 64 位[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bea0d-372">- Install 64-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="bea0d-373">-安装 64 位 LOB 客户端和其他必要的 Dll。</span><span class="sxs-lookup"><span data-stu-id="bea0d-373">- Install 64-bit LOB client and other required DLLs.</span></span>|<span data-ttu-id="bea0d-374">**对于 32 位 BizTalk 进程**:</span><span class="sxs-lookup"><span data-stu-id="bea0d-374">**For a 32-bit BizTalk process**:</span></span><br /><br /> <span data-ttu-id="bea0d-375">-安装 64 位[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bea0d-375">- Install 64-bit [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="bea0d-376">-安装 32 位[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bea0d-376">- Install 32-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="bea0d-377">-安装 32 位 LOB 客户端和其他必要的 Dll。</span><span class="sxs-lookup"><span data-stu-id="bea0d-377">- Install 32-bit LOB client and other required DLLs.</span></span><br /><br /> <span data-ttu-id="bea0d-378">**对于 64 位 BizTalk 进程**:</span><span class="sxs-lookup"><span data-stu-id="bea0d-378">**For a 64-bit BizTalk process**:</span></span><br /><br /> <span data-ttu-id="bea0d-379">-安装 64 位[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bea0d-379">- Install 64-bit [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="bea0d-380">-安装 64 位[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bea0d-380">- Install 64-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="bea0d-381">-安装 64 位 LOB 客户端和其他必要的 Dll。</span><span class="sxs-lookup"><span data-stu-id="bea0d-381">- Install 64-bit LOB client and other required DLLs.</span></span><br /><br /> <span data-ttu-id="bea0d-382">-安装 32 位[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bea0d-382">- Install 32-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="bea0d-383">-安装 32 位 LOB 客户端和其他必要的 Dll。</span><span class="sxs-lookup"><span data-stu-id="bea0d-383">- Install 32-bit LOB client and other required DLLs.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="bea0d-384">在你想要执行设计时任务的任何计算机上使用[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]或者 BizTalk MMC 中，则必须安装 32 位[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bea0d-384">On any computer where you want to do design-time tasks, using either [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] or BizTalk MMC, you must install the 32-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span>  
  
<a name="BKMK_Install_wizard"></a>   
### <a name="installing-the-biztalk-adapter-pack-in-interactive-mode"></a><span data-ttu-id="bea0d-385">在交互模式中安装 BizTalk 适配器包</span><span class="sxs-lookup"><span data-stu-id="bea0d-385">Installing the BizTalk Adapter Pack in interactive mode</span></span>  
<span data-ttu-id="bea0d-386">完成以下步骤以安装[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]使用安装向导。</span><span class="sxs-lookup"><span data-stu-id="bea0d-386">Complete the following steps to install the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] using the setup wizard.</span></span>  
  
1.  <span data-ttu-id="bea0d-387">从[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装媒体上，运行**Setup.exe**。</span><span class="sxs-lookup"><span data-stu-id="bea0d-387">From the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation media, run **Setup.exe**.</span></span>  
  
2.  <span data-ttu-id="bea0d-388">选择**安装 Microsoft BizTalk 适配器**。</span><span class="sxs-lookup"><span data-stu-id="bea0d-388">Select **Install Microsoft BizTalk Adapters**.</span></span> <span data-ttu-id="bea0d-389">在下一步的窗口中，选择**安装 Microsoft BizTalk 适配器包**或**安装 Microsoft BizTalk 适配器包 (x64)**，取决于你的平台。</span><span class="sxs-lookup"><span data-stu-id="bea0d-389">In the next window, select **Install Microsoft BizTalk Adapter Pack** or **Install Microsoft BizTalk Adapter Pack (x64)**, depending on your platform.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bea0d-390">如果你正在安装[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]上虚拟机，安装向导可能不会继续超出了通知，安装程序正在检查可用磁盘空间的对话框。</span><span class="sxs-lookup"><span data-stu-id="bea0d-390">If you are installing the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] on a virtual machine, the setup wizard might not proceed beyond a dialog box informing that the setup is checking for available disk space.</span></span> <span data-ttu-id="bea0d-391">在这种情况下，我们建议你使用的无提示安装选项。</span><span class="sxs-lookup"><span data-stu-id="bea0d-391">In such cases, we recommend that you use the silent installation option.</span></span> <span data-ttu-id="bea0d-392">请参阅[在无提示模式下安装 BizTalk 适配器包](#BKMK_SilentInst)（本主题中）。</span><span class="sxs-lookup"><span data-stu-id="bea0d-392">See [Installing the BizTalk Adapter Pack in Silent Mode](#BKMK_SilentInst) (in this topic).</span></span>  
  
3.  <span data-ttu-id="bea0d-393">在欢迎屏幕上，选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="bea0d-393">On the Welcome screen, select **Next**.</span></span>  
  
4.  <span data-ttu-id="bea0d-394">接受最终用户许可协议 (EULA)，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="bea0d-394">Accept the end-user license agreement (EULA), and then select **Next**.</span></span>  
  
5.  <span data-ttu-id="bea0d-395">在**选择安装类型**:</span><span class="sxs-lookup"><span data-stu-id="bea0d-395">In **Choose Setup Type**:</span></span>  
  
    -   <span data-ttu-id="bea0d-396">若要安装的最常见的功能，请选择**典型**。</span><span class="sxs-lookup"><span data-stu-id="bea0d-396">To install the most common features, select **Typical**.</span></span>  
  
    -   <span data-ttu-id="bea0d-397">若要选择你想要安装的适配器，选择**自定义**，然后继续下一步。</span><span class="sxs-lookup"><span data-stu-id="bea0d-397">To select the adapters you want to install, select **Custom**, and then proceed to the next step.</span></span>  
  
    -   <span data-ttu-id="bea0d-398">若要安装所有功能，请选择**完成**。</span><span class="sxs-lookup"><span data-stu-id="bea0d-398">To install all the features, select **Complete**.</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="bea0d-399">若要安装使用要与企业应用程序之间的接口，请选择适配器**自定义**安装。</span><span class="sxs-lookup"><span data-stu-id="bea0d-399">To install only the adapter that you use to interface with your enterprise application, select the **Custom** installation.</span></span>  
  
6. <span data-ttu-id="bea0d-400">**所需**仅在您选择自定义安装。</span><span class="sxs-lookup"><span data-stu-id="bea0d-400">**Required** only if you chose the Custom installation.</span></span> <span data-ttu-id="bea0d-401">如果你选择了**典型**或**完成**安装，然后跳过此步骤中，并转到步骤 7。</span><span class="sxs-lookup"><span data-stu-id="bea0d-401">If you chose the **Typical** or **Complete** installation, then skip this step, and go to step 7.</span></span>  
  
    1.  <span data-ttu-id="bea0d-402">在**自定义安装**，展开**基适配器**若要查看可用的适配器。</span><span class="sxs-lookup"><span data-stu-id="bea0d-402">In **Custom Setup**, expand **Base Adapters** to see the available adapters.</span></span>  
  
    2.  <span data-ttu-id="bea0d-403">对于你不希望的适配器，选择该适配器旁边的图标，然后选择**整个功能将不可**。</span><span class="sxs-lookup"><span data-stu-id="bea0d-403">For the adapters that you don't want, select the icon next to the adapter, and then select **Entire feature will be unavailable**.</span></span>  
  
    3.  <span data-ttu-id="bea0d-404">展开**ADO 提供程序**，然后选择你不想要安装的提供程序。</span><span class="sxs-lookup"><span data-stu-id="bea0d-404">Expand **ADO Providers**, and then select the providers that you don't want to install.</span></span>  
  
    4.  <span data-ttu-id="bea0d-405">选择“下一步” 。</span><span class="sxs-lookup"><span data-stu-id="bea0d-405">Select **Next**.</span></span>  
  
7.  <span data-ttu-id="bea0d-406">选择“安装”。</span><span class="sxs-lookup"><span data-stu-id="bea0d-406">Select **Install**.</span></span>  
  
8.  <span data-ttu-id="bea0d-407">在**客户体验改善计划**，你可以选择注册。</span><span class="sxs-lookup"><span data-stu-id="bea0d-407">In **Customer Experience Improvement Program**, you can choose to enroll.</span></span> <span data-ttu-id="bea0d-408">如果注册后，你可以与 Microsoft 共享的下列数据：</span><span class="sxs-lookup"><span data-stu-id="bea0d-408">If you enroll, you can share the following data with Microsoft:</span></span>  
  
    -   <span data-ttu-id="bea0d-409">与你正在其安装的计算机硬件相关的数据[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bea0d-409">Data related to the computer hardware on which you are installing the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span>  
  
    -   <span data-ttu-id="bea0d-410">与你使用的企业应用程序版本相关的数据[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bea0d-410">Data related to the enterprise application versions you are using with the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span>  
  
     <span data-ttu-id="bea0d-411">选择“确定”。</span><span class="sxs-lookup"><span data-stu-id="bea0d-411">Select **OK**.</span></span> <span data-ttu-id="bea0d-412">[CEIP](http://go.microsoft.com/fwlink/p/?LinkId=144699)提供了详细信息。</span><span class="sxs-lookup"><span data-stu-id="bea0d-412">[CEIP](http://go.microsoft.com/fwlink/p/?LinkId=144699) provides more information.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bea0d-413">你始终可以通过在从修复模式下运行安装程序来更改此设置**程序**。</span><span class="sxs-lookup"><span data-stu-id="bea0d-413">You can always change this setting by running the Setup in Repair mode from **Programs**.</span></span>  
  
9. <span data-ttu-id="bea0d-414">选择“完成”。</span><span class="sxs-lookup"><span data-stu-id="bea0d-414">Select **Finish**.</span></span>  
  
<a name="BKMK_SilentInst"></a>   
### <a name="installing-the-biztalk-adapter-pack-in-silent-mode"></a><span data-ttu-id="bea0d-415">在无提示模式下安装 BizTalk 适配器包</span><span class="sxs-lookup"><span data-stu-id="bea0d-415">Installing the BizTalk Adapter Pack in silent mode</span></span>  
 <span data-ttu-id="bea0d-416">使用**msiexec**命令以执行无提示安装。</span><span class="sxs-lookup"><span data-stu-id="bea0d-416">Use the **msiexec** command to do a silent installation.</span></span> <span data-ttu-id="bea0d-417">作为 msiexec 命令的一部分，输入你想要安装的各个组件。</span><span class="sxs-lookup"><span data-stu-id="bea0d-417">As part of the msiexec command, enter the individual components that you want to install.</span></span> <span data-ttu-id="bea0d-418">下表列出了每个组件值[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bea0d-418">The following table lists the values for each component in the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="bea0d-419">使用这些值来安装 （或删除） 特定的组件。</span><span class="sxs-lookup"><span data-stu-id="bea0d-419">Use these values to install (or remove) specific components.</span></span> <span data-ttu-id="bea0d-420">若要安装 （或删除） 多个组件，可以使用由逗号分隔这些值的组合。</span><span class="sxs-lookup"><span data-stu-id="bea0d-420">To install (or remove) more than one component, you can use a combination of these values separated by a comma.</span></span>  
  
|<span data-ttu-id="bea0d-421">组件名称</span><span class="sxs-lookup"><span data-stu-id="bea0d-421">Component name</span></span>|<span data-ttu-id="bea0d-422">对应的命令行属性值</span><span class="sxs-lookup"><span data-stu-id="bea0d-422">Corresponding value for command-line properties</span></span>|  
|---|---|  
|[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]|<span data-ttu-id="bea0d-423">DbFeature</span><span class="sxs-lookup"><span data-stu-id="bea0d-423">DbFeature</span></span>|  
|[!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)]|<span data-ttu-id="bea0d-424">OracleEBSFeature</span><span class="sxs-lookup"><span data-stu-id="bea0d-424">OracleEBSFeature</span></span>|  
|[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]|<span data-ttu-id="bea0d-425">SapBaseAdapterFeature</span><span class="sxs-lookup"><span data-stu-id="bea0d-425">SapBaseAdapterFeature</span></span>|  
|[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]|<span data-ttu-id="bea0d-426">SiebelBaseAdapterFeature</span><span class="sxs-lookup"><span data-stu-id="bea0d-426">SiebelBaseAdapterFeature</span></span>|  
|[!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]|<span data-ttu-id="bea0d-427">SqlFeature</span><span class="sxs-lookup"><span data-stu-id="bea0d-427">SqlFeature</span></span>|  
|[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]|<span data-ttu-id="bea0d-428">SapAdoFeature</span><span class="sxs-lookup"><span data-stu-id="bea0d-428">SapAdoFeature</span></span><br /><br /> <span data-ttu-id="bea0d-429">**请注意**： 必须提供此值，仅当你安装[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]还。</span><span class="sxs-lookup"><span data-stu-id="bea0d-429">**Note**: You must provide this value only if you are installing the [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)] also.</span></span>|  
|[!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]|<span data-ttu-id="bea0d-430">SiebelAdoFeature</span><span class="sxs-lookup"><span data-stu-id="bea0d-430">SiebelAdoFeature</span></span><br /><br /> <span data-ttu-id="bea0d-431">**请注意**： 必须提供此值，仅当你安装[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]还。</span><span class="sxs-lookup"><span data-stu-id="bea0d-431">**Note**: You must provide this value only if you are installing the [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)] also.</span></span>|  
|<span data-ttu-id="bea0d-432">所有组件</span><span class="sxs-lookup"><span data-stu-id="bea0d-432">All components</span></span>|<span data-ttu-id="bea0d-433">ALL</span><span class="sxs-lookup"><span data-stu-id="bea0d-433">ALL</span></span>|  
  
> [!IMPORTANT]
>  <span data-ttu-id="bea0d-434">功能名称是区分大小写。</span><span class="sxs-lookup"><span data-stu-id="bea0d-434">The feature names are case-sensitive.</span></span>  
  
 <span data-ttu-id="bea0d-435">以下步骤显示如何完成的无提示安装[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]不同组件。</span><span class="sxs-lookup"><span data-stu-id="bea0d-435">The following steps show you how to complete a silent installation of [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] for different components.</span></span>  
  
##### <a name="install-in-silent-mode"></a><span data-ttu-id="bea0d-436">在无提示模式下安装</span><span class="sxs-lookup"><span data-stu-id="bea0d-436">Install in silent mode</span></span>  
  
1.  <span data-ttu-id="bea0d-437">打开命令提示符，并转到[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]根中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装。</span><span class="sxs-lookup"><span data-stu-id="bea0d-437">Open a command prompt, and go to the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] root in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation.</span></span>  
  
2.  <span data-ttu-id="bea0d-438">运行基于你想要安装的以下命令：</span><span class="sxs-lookup"><span data-stu-id="bea0d-438">Run the following commands based on what you want to install:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bea0d-439">若要执行无提示安装在基于 x64 的平台上，将`AdaptersSetup.msi`与`AdaptersSetup64.msi`以下命令中。</span><span class="sxs-lookup"><span data-stu-id="bea0d-439">To do silent installation on an x64-based platform, replace `AdaptersSetup.msi` with `AdaptersSetup64.msi` in the following commands.</span></span>  
  
    -   <span data-ttu-id="bea0d-440">若要执行的完整安装，安装所有适配器包括.NET Framework 数据提供程序，请键入：</span><span class="sxs-lookup"><span data-stu-id="bea0d-440">To perform a complete installation, which installs all the adapters including the .NET Framework Data Providers, type:</span></span>  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=ALL  
        ```  
  
    -   <span data-ttu-id="bea0d-441">仅安装[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]，类型：</span><span class="sxs-lookup"><span data-stu-id="bea0d-441">To install only the [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)], type:</span></span>  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=DbFeature  
        ```  
  
    -   <span data-ttu-id="bea0d-442">仅安装[!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)]，类型：</span><span class="sxs-lookup"><span data-stu-id="bea0d-442">To install only the [!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)], type:</span></span>  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=OracleEBSFeature  
        ```  
  
    -   <span data-ttu-id="bea0d-443">仅安装[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]，类型：</span><span class="sxs-lookup"><span data-stu-id="bea0d-443">To install only the [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)], type:</span></span>  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapBaseAdapterFeature  
        ```  
  
    -   <span data-ttu-id="bea0d-444">若要安装[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]连同[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]，类型：</span><span class="sxs-lookup"><span data-stu-id="bea0d-444">To install the [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)] along with [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)], type:</span></span>  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapBaseAdapterFeature,SapAdoFeature  
        ```  
  
    -   <span data-ttu-id="bea0d-445">仅安装[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]，类型：</span><span class="sxs-lookup"><span data-stu-id="bea0d-445">To install only the [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)], type:</span></span>  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SiebelBaseAdapterFeature  
        ```  
  
    -   <span data-ttu-id="bea0d-446">若要安装[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]连同[!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]，类型：</span><span class="sxs-lookup"><span data-stu-id="bea0d-446">To install the [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)] along with [!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)], type:</span></span>  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SiebelBaseAdapterFeature,SiebelAdoFeature  
        ```  
  
    -   <span data-ttu-id="bea0d-447">仅安装[!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]，类型：</span><span class="sxs-lookup"><span data-stu-id="bea0d-447">To install only the [!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)], type:</span></span>  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SqlFeature  
        ```  
  
    -   <span data-ttu-id="bea0d-448">若要安装的所有基适配器，请键入：</span><span class="sxs-lookup"><span data-stu-id="bea0d-448">To install all the base adapters, type:</span></span>  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapBaseAdapterFeature,SiebelBaseAdapterFeature,DbFeature,OracleEBSFeature,SqlFeature  
        ```  
  
    -   <span data-ttu-id="bea0d-449">若要安装两个.NET Framework 数据提供程序，请键入：</span><span class="sxs-lookup"><span data-stu-id="bea0d-449">To install the two .NET Framework Data Providers, type:</span></span>  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapAdoFeature,SiebelAdoFeature  
        ```  
  
    -   <span data-ttu-id="bea0d-450">任何类型的以逗号分隔各个组件的自定义安装。</span><span class="sxs-lookup"><span data-stu-id="bea0d-450">Any type of custom installation by separating the components by a comma.</span></span> <span data-ttu-id="bea0d-451">例如，若要安装[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]与[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]，和[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]类型：</span><span class="sxs-lookup"><span data-stu-id="bea0d-451">For example, to install the [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)] with the [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)], and the [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)] type:</span></span>  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapBaseAdapterFeature,SapAdoFeature,SiebelBaseAdapterFeature  
        ```  
  
    -   <span data-ttu-id="bea0d-452">你还可以选择注册 CEIP 的无提示安装的一部分。</span><span class="sxs-lookup"><span data-stu-id="bea0d-452">You can also opt to enroll for CEIP as part of the silent installation.</span></span> <span data-ttu-id="bea0d-453">类型：</span><span class="sxs-lookup"><span data-stu-id="bea0d-453">Type:</span></span>  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn CEIP_OPTIN=true  
        ```  
  
         <span data-ttu-id="bea0d-454">默认情况下该选项为 false。</span><span class="sxs-lookup"><span data-stu-id="bea0d-454">By default the option is false.</span></span> 
  
        > [!IMPORTANT]
        >  <span data-ttu-id="bea0d-455">安装时[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]在静默模式下的评估版，CEIP 的默认选项为 true。</span><span class="sxs-lookup"><span data-stu-id="bea0d-455">While installing the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] Evaluation version in silent mode, the default option for CEIP is true.</span></span>  
  
     <span data-ttu-id="bea0d-456">有关 msiexec 命令类型的详细信息`msiexec`上的命令行和按`ENTER`。</span><span class="sxs-lookup"><span data-stu-id="bea0d-456">For more information about the msiexec command type `msiexec` on the command line and press `ENTER`.</span></span> <span data-ttu-id="bea0d-457">或转到[http://go.microsoft.com/fwlink/p/?LinkId=103199](http://go.microsoft.com/fwlink/p/?LinkId=103199)。</span><span class="sxs-lookup"><span data-stu-id="bea0d-457">Or go to [http://go.microsoft.com/fwlink/p/?LinkId=103199](http://go.microsoft.com/fwlink/p/?LinkId=103199).</span></span>
  
<a name="BKMK_PostInst"></a>   
### <a name="after-installing-the-biztalk-adapter-pack"></a><span data-ttu-id="bea0d-458">安装 BizTalk 适配器包后</span><span class="sxs-lookup"><span data-stu-id="bea0d-458">After installing the BizTalk Adapter Pack</span></span>  
 <span data-ttu-id="bea0d-459">你可能需要在安装后执行以下任务[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]，将根据你想要与每个适配器执行哪些操作：</span><span class="sxs-lookup"><span data-stu-id="bea0d-459">You may need to do the following tasks after installing the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)], based on what operations you want to do with each adapter:</span></span>  
  
-   <span data-ttu-id="bea0d-460">[配置 Oracle 数据库适配器，以使用较新的 Oracle.DataAccess.dll 版本](#BKMK_ConfigNewOracleDLL)OracleDB 配置文件中。</span><span class="sxs-lookup"><span data-stu-id="bea0d-460">[Configure the Oracle Database adapter to use a newer Oracle.DataAccess.dll version](#BKMK_ConfigNewOracleDLL) in the OracleDB configuration file.</span></span>  
  
-   <span data-ttu-id="bea0d-461">[（仅为 SAP 适配器中） 创建 SQL Server 数据库对象](#BKMK_CreateSQLServer)来调用中某个 SAP 系统的事务性 Rfc (tRFCs)。</span><span class="sxs-lookup"><span data-stu-id="bea0d-461">[Create SQL Server Database Objects (Only for the SAP Adapter)](#BKMK_CreateSQLServer) to invoke transactional RFCs (tRFCs) in an SAP system.</span></span>  
  
-   <span data-ttu-id="bea0d-462">[注册的适配器绑定](#BKMK_Register_Bindings)与.NET Framework 数据提供程序安装向导时若要这样做。</span><span class="sxs-lookup"><span data-stu-id="bea0d-462">[Register the adapter bindings](#BKMK_Register_Bindings) and the .NET Framework Data Providers if the setup wizard fails to do so.</span></span>  
  
-   <span data-ttu-id="bea0d-463">[确定的公钥和版本](#BKMK_PubKey)的其他适配器文件。</span><span class="sxs-lookup"><span data-stu-id="bea0d-463">[Determine the Public Key and Version](#BKMK_PubKey) of the different adapter files.</span></span>  
  
-   <span data-ttu-id="bea0d-464">[安装自定义 Rfc](#BKMK_InstallCustomRFC)如果你选择安装[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bea0d-464">[Install the Custom RFCs](#BKMK_InstallCustomRFC) if you chose to install the [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)].</span></span>  
  
<a name="BKMK_ConfigNewOracleDLL"></a>   
#### <a name="configure-the-oracle-database-adapter-to-use-a-newer-oracledataaccessdll-version"></a><span data-ttu-id="bea0d-465">配置 Oracle 数据库适配器，以使用较新的 Oracle.DataAccess.dll 版本</span><span class="sxs-lookup"><span data-stu-id="bea0d-465">Configure the Oracle Database adapter to use a newer Oracle.DataAccess.dll version</span></span>  
 <span data-ttu-id="bea0d-466">当配置要使用 WCF OracleDB 适配器，或者使用 Visual Studio 使用的生成的适配器的端口时，显示一条消息，该适配器需要 Oracle.DataAccess.dll 版本 2.111.7.0。</span><span class="sxs-lookup"><span data-stu-id="bea0d-466">When you configure a port to use the WCF-OracleDB adapter or use Visual Studio to consume a generated adapter, a message displays that the adapter needs Oracle.DataAccess.dll version 2.111.7.0.</span></span> <span data-ttu-id="bea0d-467">若要解决此消息，请安装支持的 Oracle.DataAccess.dll 版本 (请参阅[支持版本列表](https://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx))，然后更新`bindingRedirect`OracleDB 配置文件中的元素。</span><span class="sxs-lookup"><span data-stu-id="bea0d-467">To resolve this message, install a supported Oracle.DataAccess.dll version (see [supported version list](https://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)), and then update the `bindingRedirect` element in the OracleDB configuration file.</span></span> <span data-ttu-id="bea0d-468">步骤：</span><span class="sxs-lookup"><span data-stu-id="bea0d-468">Steps:</span></span>  
  
1.  <span data-ttu-id="bea0d-469">在 BizTalk Server 中，转到以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="bea0d-469">On the BizTalk Server, go to the following folders:</span></span>  
  
     <span data-ttu-id="bea0d-470">*驱动器*: files\microsoft BizTalk 适配器包 (x64) \bin</span><span class="sxs-lookup"><span data-stu-id="bea0d-470">*drive*:\Program Files\Microsoft BizTalk Adapter Pack(x64)\bin</span></span>  
  
     <span data-ttu-id="bea0d-471">*驱动器*: \Program 文件 (x86) \Microsoft BizTalk Adapter Pack\bin</span><span class="sxs-lookup"><span data-stu-id="bea0d-471">*drive*:\Program Files (x86)\Microsoft BizTalk Adapter Pack\bin</span></span>  
  
2.  <span data-ttu-id="bea0d-472">打开 Microsoft.Adapters.OracleDB.config 文件。</span><span class="sxs-lookup"><span data-stu-id="bea0d-472">Open the Microsoft.Adapters.OracleDB.config file.</span></span>  
  
3.  <span data-ttu-id="bea0d-473">找到以下部分中，并复制/粘贴以下内容：</span><span class="sxs-lookup"><span data-stu-id="bea0d-473">Find the following section, and copy/paste the following:</span></span>  
  
    ```  
    <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
              <dependentAssembly>  
                        <assemblyIdentity name="Oracle.DataAccess" publicKeyToken="89b483f429c47342" culture="neutral" />  
                        <bindingRedirect oldVersion="2.111.7.00" newVersion="2.112.1.00"/>  
              </dependentAssembly>  
    </assemblyBinding>  
  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="bea0d-474">在此示例中，我们将设置*newVersion*到 2.112.1.00。</span><span class="sxs-lookup"><span data-stu-id="bea0d-474">In this example, we set *newVersion* to 2.112.1.00.</span></span> <span data-ttu-id="bea0d-475">将此值设置为已安装的版本。</span><span class="sxs-lookup"><span data-stu-id="bea0d-475">Set this value to the version you have installed.</span></span>  
  
> [!IMPORTANT]
>  -   <span data-ttu-id="bea0d-476">如果此组中有多个 BizTalk 服务器，请在组中的所有 BizTalk 服务器上进行此更改。</span><span class="sxs-lookup"><span data-stu-id="bea0d-476">If there are multiple BizTalk Servers in this group, make this change on all the BizTalk servers in the group.</span></span>  
> -   <span data-ttu-id="bea0d-477">*NewVersion*值需要更新的计算机上安装的 Oracle.DataAccess.dll 文件的版本。</span><span class="sxs-lookup"><span data-stu-id="bea0d-477">The *newVersion* value needs to be updated based on the version of the Oracle.DataAccess.dll file installed on the computer.</span></span>  <span data-ttu-id="bea0d-478">Oracle.DataAccess.dll 都附带从 Oracle 安装 Oracle 客户端。</span><span class="sxs-lookup"><span data-stu-id="bea0d-478">Oracle.DataAccess.dll is included with the Oracle Client you install from Oracle.</span></span>  <span data-ttu-id="bea0d-479">你只需安装的 Oracle 客户端版本[的 BizTalk 适配器包支持](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)。</span><span class="sxs-lookup"><span data-stu-id="bea0d-479">You must only install an Oracle Client version that is [supported by the BizTalk Adapter Pack](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx).</span></span>  
  
<a name="BKMK_CreateSQLServer"></a>   
#### <a name="create-sql-server-database-objects-only-for-the-sap-adapter"></a><span data-ttu-id="bea0d-480">创建 SQL Server 数据库对象 （仅适用于 SAP 适配器）</span><span class="sxs-lookup"><span data-stu-id="bea0d-480">Create SQL Server Database objects (only for the SAP adapter)</span></span>  
 <span data-ttu-id="bea0d-481">若要调用 tRFCs SAP 系统中，运行*SapAdapter DbScript Install.sql* SQL 脚本。</span><span class="sxs-lookup"><span data-stu-id="bea0d-481">To invoke tRFCs in an SAP system, run the *SapAdapter-DbScript-Install.sql* SQL script.</span></span> <span data-ttu-id="bea0d-482">此脚本安装使用[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]安装，并在 SQL Server 中创建数据库对象。</span><span class="sxs-lookup"><span data-stu-id="bea0d-482">This script is installed with the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] installation, and creates database objects in SQL Server.</span></span> <span data-ttu-id="bea0d-483">该脚本通常安装在\<安装驱动器 >: files\microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bea0d-483">The script is typically installed at \<installation drive>:\Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="bea0d-484">只要在使用该适配器调用 tRFCs 时输入该数据库名称，你可以针对任何 SQL Server 数据库，运行此脚本。</span><span class="sxs-lookup"><span data-stu-id="bea0d-484">You can run this script against any SQL Server database, as long as you enter that database name while using the adapter to invoke tRFCs.</span></span>  
  
<a name="BKMK_Register_Bindings"></a>   
#### <a name="register-the-adapter-bindings"></a><span data-ttu-id="bea0d-485">注册的适配器绑定</span><span class="sxs-lookup"><span data-stu-id="bea0d-485">Register the adapter bindings</span></span>  
 <span data-ttu-id="bea0d-486">期间[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]安装，安装向导可能无法注册的适配器绑定或.NET Framework 数据提供程序 mySAP Business Suite，但安装程序将继续执行适配器安装。</span><span class="sxs-lookup"><span data-stu-id="bea0d-486">During the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] installation, the setup wizard may fail to register the adapter bindings or the .NET Framework Data Provider for mySAP Business Suite, but setup proceeds with the adapter installation.</span></span> <span data-ttu-id="bea0d-487">这可能会由于使用 Windows Communication Foundation (WCF) 安装时，问题而导致[!INCLUDE[afproductnamelong](../includes/afproductnamelong-md.md)]安装或被损坏的 machine.config 文件。</span><span class="sxs-lookup"><span data-stu-id="bea0d-487">This might result due to problems with Windows Communication Foundation (WCF) installation, [!INCLUDE[afproductnamelong](../includes/afproductnamelong-md.md)] installation, or the machine.config file being corrupt.</span></span>  
  
<span data-ttu-id="bea0d-488">完成这些步骤*仅*如果安装向导无法在 machine.config 文件中注册的适配器绑定或.NET Framework 数据提供程序。</span><span class="sxs-lookup"><span data-stu-id="bea0d-488">Complete these steps *only* if the setup wizard fails to register the adapter bindings or .NET Framework Data Providers in the machine.config file.</span></span>  
  
###### <a name="register-the-adapter-bindings-or-the-net-framework-data-providers"></a><span data-ttu-id="bea0d-489">注册的适配器绑定或.NET Framework 数据提供程序</span><span class="sxs-lookup"><span data-stu-id="bea0d-489">Register the adapter bindings or the .NET Framework data providers</span></span>  
  
1.  <span data-ttu-id="bea0d-490">转到计算机上的 machine.config 文件。</span><span class="sxs-lookup"><span data-stu-id="bea0d-490">Go to the machine.config file on the computer.</span></span> <span data-ttu-id="bea0d-491">例如，在 32 位平台上，machine.config 位于下\<系统驱动器 >: \WINDOWS\Microsoft.NET\Framework\\< 版本\>\CONFIG。</span><span class="sxs-lookup"><span data-stu-id="bea0d-491">For example, on a 32-bit platform, the machine.config is available under \<system drive>:\WINDOWS\Microsoft.NET\Framework\\<version\>\CONFIG.</span></span>  
  
2.  <span data-ttu-id="bea0d-492">打开使用文本编辑器的文件。</span><span class="sxs-lookup"><span data-stu-id="bea0d-492">Open the file using a text editor.</span></span>  
  
3.  <span data-ttu-id="bea0d-493">注册的适配器绑定：</span><span class="sxs-lookup"><span data-stu-id="bea0d-493">Register the adapter bindings:</span></span>  
  
    1.  <span data-ttu-id="bea0d-494">搜索`system.serviceModel`元素，并添加其下的以下：</span><span class="sxs-lookup"><span data-stu-id="bea0d-494">Search for the `system.serviceModel` element, and add the following under it:</span></span>  
  
        ```  
        <client>  
          <endpoint binding="sapBinding" contract="IMetadataExchange" name="sap" />  
          <endpoint binding="siebelBinding" contract="IMetadataExchange" name="siebel" />  
          <endpoint binding="oracleDBBinding" contract="IMetadataExchange" name="oracleDb" />  
          <endpoint binding="oracleEBSBinding" contract="IMetadataExchange" name="oracleEBS" />  
          <endpoint binding="sqlBinding" contract="IMetadataExchange" name="mssql" />  
        </client>  
        ```  
  
    2.  <span data-ttu-id="bea0d-495">搜索`bindingElementExtensions`system.serviceModel\extensions 下的元素。</span><span class="sxs-lookup"><span data-stu-id="bea0d-495">Search for the `bindingElementExtensions` element under system.serviceModel\extensions.</span></span>  
  
    3.  <span data-ttu-id="bea0d-496">查找缺失的适配器绑定。</span><span class="sxs-lookup"><span data-stu-id="bea0d-496">Look for the missing adapter binding.</span></span> <span data-ttu-id="bea0d-497">添加以下各节下的`bindingElementExtensions`节点，具体取决于缺少的适配器绑定。</span><span class="sxs-lookup"><span data-stu-id="bea0d-497">Add the following sections under the `bindingElementExtensions` node, depending on the missing adapter binding.</span></span> <span data-ttu-id="bea0d-498">如果安装向导无法注册任何，则必须注册的所有绑定。</span><span class="sxs-lookup"><span data-stu-id="bea0d-498">You must register all the bindings if the setup wizard fails to register any.</span></span>  
  
         <span data-ttu-id="bea0d-499">有关[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]，添加：</span><span class="sxs-lookup"><span data-stu-id="bea0d-499">For the [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)], add:</span></span>  
  
        ```  
        <add name="sapAdapter" type="Microsoft.Adapters.SAP.SAPAdapterExtensionElement,Microsoft.Adapters.SAP, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         <span data-ttu-id="bea0d-500">有关[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]，添加：</span><span class="sxs-lookup"><span data-stu-id="bea0d-500">For the [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)], add:</span></span>  
  
        ```  
        <add name="siebelAdapter" type="Microsoft.Adapters.Siebel.SiebelAdapterExtensionElement,Microsoft.Adapters.Siebel, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         <span data-ttu-id="bea0d-501">有关[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]，添加：</span><span class="sxs-lookup"><span data-stu-id="bea0d-501">For the [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)], add:</span></span>  
  
        ```  
        <add name="oracleDBAdapter" type="Microsoft.Adapters.OracleDB.OracleDBAdapterExtensionElement,Microsoft.Adapters.OracleDB, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         <span data-ttu-id="bea0d-502">有关[!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)]，添加：</span><span class="sxs-lookup"><span data-stu-id="bea0d-502">For the [!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)], add:</span></span>  
  
        ```  
        <add name="OracleEBSAdapter" type="Microsoft.Adapters.OracleEBS.OracleEBSBindingElementExtensionElement, Microsoft.Adapters.OracleEBS, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         <span data-ttu-id="bea0d-503">有关[!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]，添加：</span><span class="sxs-lookup"><span data-stu-id="bea0d-503">For the [!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)], add:</span></span>  
  
        ```  
        <add name="sqlAdapter" type="Microsoft.Adapters.Sql.SqlAdapterBindingElementExtensionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
    4.  <span data-ttu-id="bea0d-504">搜索`bindingExtensions`system.serviceModel\extensions 下的元素。</span><span class="sxs-lookup"><span data-stu-id="bea0d-504">Search for the `bindingExtensions` element under system.serviceModel\extensions.</span></span>  
  
    5.  <span data-ttu-id="bea0d-505">查找缺失的适配器绑定。</span><span class="sxs-lookup"><span data-stu-id="bea0d-505">Look for the missing adapter binding.</span></span> <span data-ttu-id="bea0d-506">添加以下各节下的`bindingExtensions`节点，具体取决于缺少的适配器绑定。</span><span class="sxs-lookup"><span data-stu-id="bea0d-506">Add the following sections under the `bindingExtensions` node, depending on the missing adapter binding.</span></span> <span data-ttu-id="bea0d-507">如果安装向导无法注册任何，则必须注册的所有绑定。</span><span class="sxs-lookup"><span data-stu-id="bea0d-507">You must register all the bindings if the setup wizard fails to register any.</span></span>  
  
         <span data-ttu-id="bea0d-508">有关[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]，添加：</span><span class="sxs-lookup"><span data-stu-id="bea0d-508">For [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)], add:</span></span>  
  
        ```  
        <add name="sapBinding" type="Microsoft.Adapters.SAP.SAPAdapterBindingSection,Microsoft.Adapters.SAP, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         <span data-ttu-id="bea0d-509">有关[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]，添加：</span><span class="sxs-lookup"><span data-stu-id="bea0d-509">For [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)], add:</span></span>  
  
        ```  
        <add name="siebelBinding" type="Microsoft.Adapters.Siebel.SiebelAdapterBindingSection,Microsoft.Adapters.Siebel, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         <span data-ttu-id="bea0d-510">有关[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]，添加：</span><span class="sxs-lookup"><span data-stu-id="bea0d-510">For [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)], add:</span></span>  
  
        ```  
        <add name="oracleDBBinding" type="Microsoft.Adapters.OracleDB.OracleDBAdapterBindingSection,Microsoft.Adapters.OracleDB, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         <span data-ttu-id="bea0d-511">有关[!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)]，添加：</span><span class="sxs-lookup"><span data-stu-id="bea0d-511">For [!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)], add:</span></span>  
  
        ```  
        <add name="OracleEBSBinding" type="Microsoft.Adapters.OracleEBS.OracleEBSBindingCollectionElement, Microsoft.Adapters.OracleEBS,Microsoft.Adapters.OracleEBS, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         <span data-ttu-id="bea0d-512">有关[!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]，添加：</span><span class="sxs-lookup"><span data-stu-id="bea0d-512">For [!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)], add:</span></span>  
  
        ```  
        <add name="sqlBinding" type="Microsoft.Adapters.Sql.SqlAdapterBindingCollectionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
    > [!NOTE]
    >  <span data-ttu-id="bea0d-513">有关如何确定的公钥的信息，请参阅[确定的公钥和版本](#BKMK_PubKey)。</span><span class="sxs-lookup"><span data-stu-id="bea0d-513">For information about how to determine the public key, see [Determine the Public Key and Version](#BKMK_PubKey).</span></span>  
  
4.  <span data-ttu-id="bea0d-514">注册.NET Framework 数据提供程序：</span><span class="sxs-lookup"><span data-stu-id="bea0d-514">Register the .NET Framework data providers:</span></span>  
  
    1.  <span data-ttu-id="bea0d-515">搜索`DbProviderFactories`system.data 节点下的元素。</span><span class="sxs-lookup"><span data-stu-id="bea0d-515">Search for the `DbProviderFactories` element under the system.data node.</span></span>  
  
    2.  <span data-ttu-id="bea0d-516">查找缺少的.NET Framework 数据提供程序。</span><span class="sxs-lookup"><span data-stu-id="bea0d-516">Look for the missing .NET Framework Data Providers.</span></span> <span data-ttu-id="bea0d-517">添加以下各节下的`DbProviderFactories`节点，具体取决于缺少提供程序。</span><span class="sxs-lookup"><span data-stu-id="bea0d-517">Add the following sections under the `DbProviderFactories` node, depending on the missing provider.</span></span> <span data-ttu-id="bea0d-518">如果安装向导无法注册任何，则必须注册的所有提供程序。</span><span class="sxs-lookup"><span data-stu-id="bea0d-518">You must register all the providers if the setup wizard fails to register any.</span></span>  
  
         <span data-ttu-id="bea0d-519">有关[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]，添加：</span><span class="sxs-lookup"><span data-stu-id="bea0d-519">For the [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)], add:</span></span>  
  
        ```  
        <add name="SAPClient Data Provider" invariant="Microsoft.Data.SAPClient"   
            description=".NET Framework Data Provider for mySAP Business Suite"    type="Microsoft.Data.SAPClient.SAPClientFactory,Microsoft.Data.SAPClient, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         <span data-ttu-id="bea0d-520">有关[!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]，添加：</span><span class="sxs-lookup"><span data-stu-id="bea0d-520">For the [!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)], add:</span></span>  
  
        ```  
        <add name="SiebelClient Data Provider" invariant="Microsoft.Data.SiebelClient"  
            description=".NET Framework Data Provider for Siebel eBusiness Applications"  
            type="Microsoft.Data.SiebelClient.SiebelProviderFactory,Microsoft.Data.SiebelClient, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
5.  <span data-ttu-id="bea0d-521">保存并关闭 machine.config 文件。</span><span class="sxs-lookup"><span data-stu-id="bea0d-521">Save and close the machine.config file.</span></span>  
  
<a name="BKMK_PubKey"></a>   
#### <a name="determine-the-public-key-and-version"></a><span data-ttu-id="bea0d-522">确定的公钥和版本</span><span class="sxs-lookup"><span data-stu-id="bea0d-522">Determine the Public Key and Version</span></span>  
 <span data-ttu-id="bea0d-523">完成以下步骤以确定公钥和适配器或.NET Framework 数据提供程序的版本。</span><span class="sxs-lookup"><span data-stu-id="bea0d-523">Complete the following steps to determine the public key and version for an adapter or the .NET Framework Data Provider.</span></span>  
  
###### <a name="determine-the-public-key"></a><span data-ttu-id="bea0d-524">确定的公钥</span><span class="sxs-lookup"><span data-stu-id="bea0d-524">Determine the public key</span></span>  
  
1.  <span data-ttu-id="bea0d-525">请转到 Windows 目录中，通常 C:\WINDOWS\assembly。</span><span class="sxs-lookup"><span data-stu-id="bea0d-525">Go to the Windows directory, typically C:\WINDOWS\assembly.</span></span>  
  
2.  <span data-ttu-id="bea0d-526">右键单击该 DLL 为其您希望将公钥，，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="bea0d-526">Right-click the DLL for which you want the public key, and then select **Properties**.</span></span> <span data-ttu-id="bea0d-527">下表列出的每个适配器和提供程序 Dll 的名称：</span><span class="sxs-lookup"><span data-stu-id="bea0d-527">The following table lists the name of the DLLs for each adapter and provider:</span></span>  
  
    |<span data-ttu-id="bea0d-528">适配器/.NET Framework 数据提供程序</span><span class="sxs-lookup"><span data-stu-id="bea0d-528">Adapter/.NET Framework Data Provider</span></span>|<span data-ttu-id="bea0d-529">DLL 的名称</span><span class="sxs-lookup"><span data-stu-id="bea0d-529">Name of the DLL</span></span>|  
    |---|---|  
    |[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]|<span data-ttu-id="bea0d-530">Microsoft.Adapters.SAP</span><span class="sxs-lookup"><span data-stu-id="bea0d-530">Microsoft.Adapters.SAP</span></span>|  
    |[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]|<span data-ttu-id="bea0d-531">Microsoft.Adapters.Siebel</span><span class="sxs-lookup"><span data-stu-id="bea0d-531">Microsoft.Adapters.Siebel</span></span>|  
    |[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]|<span data-ttu-id="bea0d-532">Microsoft.Adapters.OracleDB</span><span class="sxs-lookup"><span data-stu-id="bea0d-532">Microsoft.Adapters.OracleDB</span></span>|  
    |[!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)]|<span data-ttu-id="bea0d-533">Microsoft.Adapters.OracleEBS</span><span class="sxs-lookup"><span data-stu-id="bea0d-533">Microsoft.Adapters.OracleEBS</span></span>|  
    |[!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]|<span data-ttu-id="bea0d-534">Microsoft.Adapters.Sql.dll</span><span class="sxs-lookup"><span data-stu-id="bea0d-534">Microsoft.Adapters.Sql.dll</span></span>|  
    |[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]|<span data-ttu-id="bea0d-535">Microsoft.Data.SAPClient</span><span class="sxs-lookup"><span data-stu-id="bea0d-535">Microsoft.Data.SAPClient</span></span>|  
    |[!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]|<span data-ttu-id="bea0d-536">Microsoft.Data.SiebelClient</span><span class="sxs-lookup"><span data-stu-id="bea0d-536">Microsoft.Data.SiebelClient</span></span>|  
  
3.  <span data-ttu-id="bea0d-537">上**常规**选项卡上， **Public Key Token**值是 DLL 的公共密钥。</span><span class="sxs-lookup"><span data-stu-id="bea0d-537">On the **General** tab, the **Public Key Token** values is the public key for the DLL.</span></span> <span data-ttu-id="bea0d-538">**版本**值是 DLL 的版本号。</span><span class="sxs-lookup"><span data-stu-id="bea0d-538">The **Version** value is the version number for the DLL.</span></span>  
  
4.  <span data-ttu-id="bea0d-539">复制公钥，，然后选择**取消**。</span><span class="sxs-lookup"><span data-stu-id="bea0d-539">Copy the public key, and then select **Cancel**.</span></span>  
  
<a name="BKMK_InstallCustomRFC"></a>   
#### <a name="install-the-custom-rfcs"></a><span data-ttu-id="bea0d-540">安装自定义的 Rfc</span><span class="sxs-lookup"><span data-stu-id="bea0d-540">Install the custom RFCs</span></span>  
 <span data-ttu-id="bea0d-541">只需执行此任务，如果你想要使用[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bea0d-541">You only need to do this task if you want to use the [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)].</span></span> <span data-ttu-id="bea0d-542">有关安装自定义的 Rfc 的说明，请参阅[安装自定义 Rfc](../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)中[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]文档。</span><span class="sxs-lookup"><span data-stu-id="bea0d-542">For instructions on installing custom RFCs, see [Install Custom RFCs](../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md) in the [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)] documentation.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="bea0d-543">如果您将早期版本的自定义的 Rfc 随附[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]，然后必须将它们升级到此版本中提供了 Rfc。</span><span class="sxs-lookup"><span data-stu-id="bea0d-543">If you are using an earlier version of the custom RFCs provided with the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)], then you must upgrade them to the RFCs provided with this release.</span></span> <span data-ttu-id="bea0d-544">通过删除早期的 Rfc 中，执行此操作，然后安装了 Rfc 附带此版本。</span><span class="sxs-lookup"><span data-stu-id="bea0d-544">Do this by removing the earlier RFCs, and then installing the RFCs shipped with this release.</span></span>  

## <a name="installing-the-enterprise-applications"></a><span data-ttu-id="bea0d-545">安装企业应用程序</span><span class="sxs-lookup"><span data-stu-id="bea0d-545">Installing the Enterprise Applications</span></span>  
<span data-ttu-id="bea0d-546">有关步骤和指南来安装不同企业 LOB 系统，我们使用其特定安装 recommendnd 指导。</span><span class="sxs-lookup"><span data-stu-id="bea0d-546">For the steps and guidance to install the different enterprise LOB systems, we recommendnd you use their specific installation guides.</span></span> <span data-ttu-id="bea0d-547">如果任何还引用特定的配置更改，及其适配器文档。</span><span class="sxs-lookup"><span data-stu-id="bea0d-547">Also refer to its adapter documentation for specific configuration changes, if any.</span></span>   

## <a name="installation-and-post-installation-checklist"></a><span data-ttu-id="bea0d-548">安装和安装后的清单</span><span class="sxs-lookup"><span data-stu-id="bea0d-548">Installation and post-installation checklist</span></span>  
  
-   <span data-ttu-id="bea0d-549">请确保安装所有[软件必备项](#BKMK_Prereqs)使用正确的安装选项。</span><span class="sxs-lookup"><span data-stu-id="bea0d-549">Make sure you installed all the [software prerequisites](#BKMK_Prereqs) with the correct installation option.</span></span>
  
-   <span data-ttu-id="bea0d-550">请确保企业的 LOB 应用程序安装在计算机上安装受支持的版本[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bea0d-550">Make sure you have the supported version of the enterprise LOB applications installed on your computer where you installed the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="bea0d-551">请参阅[受支持的企业应用程序版本](#BKMK_SuppLOB)。</span><span class="sxs-lookup"><span data-stu-id="bea0d-551">See [Supported Enterprise Application Versions](#BKMK_SuppLOB).</span></span>  
  
-   <span data-ttu-id="bea0d-552">若要安装仅适用于企业你想要连接的 LOB 系统的适配器，请确保你安装[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]使用**自定义**安装选项。</span><span class="sxs-lookup"><span data-stu-id="bea0d-552">To install only the adapter for the enterprise LOB system you want to connect, make sure you installed the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] using the **Custom** installation option.</span></span> <span data-ttu-id="bea0d-553">请确保你安装[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]使用**完成**安装选项。</span><span class="sxs-lookup"><span data-stu-id="bea0d-553">Make sure you have not installed the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] using the **Complete** installation option.</span></span> <span data-ttu-id="bea0d-554">请参阅[安装 BizTalk 适配器包](#BKMK_Install_Adap)。</span><span class="sxs-lookup"><span data-stu-id="bea0d-554">See [Installing the BizTalk Adapter Pack](#BKMK_Install_Adap).</span></span>  
  
-   <span data-ttu-id="bea0d-555">如果你想要对 SAP 系统使用 tRFC 调用[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]，请确保 SQL Server 数据库中创建所需的表。</span><span class="sxs-lookup"><span data-stu-id="bea0d-555">If you want to make tRFC calls to the SAP system using the [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)], make sure you create the required tables in a SQL Server database.</span></span> <span data-ttu-id="bea0d-556">请参阅[安装 BizTalk 适配器包后](#BKMK_PostInst)。</span><span class="sxs-lookup"><span data-stu-id="bea0d-556">See [After Installing the BizTalk Adapter Pack](#BKMK_PostInst).</span></span>
  
-   <span data-ttu-id="bea0d-557">在运行时[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]安装向导中，你可能会收到一个表明安装程序无法注册绑定的错误消息。</span><span class="sxs-lookup"><span data-stu-id="bea0d-557">While running the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] setup wizard, you may get an error message that states the setup failed to register the bindings.</span></span> <span data-ttu-id="bea0d-558">如果是这样，则手动注册它们。</span><span class="sxs-lookup"><span data-stu-id="bea0d-558">If so, register them manually.</span></span> <span data-ttu-id="bea0d-559">请参阅[安装 BizTalk 适配器包后](#BKMK_PostInst)。</span><span class="sxs-lookup"><span data-stu-id="bea0d-559">See [After Installing the BizTalk Adapter Pack](#BKMK_PostInst).</span></span>  
  
-   <span data-ttu-id="bea0d-560">如果你选择安装[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]作为的一部分[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]安装，请确保在 SAP 系统上安装了自定义的 Rfc。</span><span class="sxs-lookup"><span data-stu-id="bea0d-560">If you chose to install the [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)] as part of the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] installation, make sure you install the custom RFCs on the SAP system.</span></span> <span data-ttu-id="bea0d-561">请参阅[安装 BizTalk 适配器包后](#BKMK_PostInst)。</span><span class="sxs-lookup"><span data-stu-id="bea0d-561">See [After Installing the BizTalk Adapter Pack](#BKMK_PostInst).</span></span>  
  
<a name="BKMK_Modify_Adap"></a>   
## <a name="change-the-biztalk-adapter-pack-installation"></a><span data-ttu-id="bea0d-562">更改 BizTalk 适配器包安装</span><span class="sxs-lookup"><span data-stu-id="bea0d-562">Change the BizTalk Adapter Pack installation</span></span>  
 <span data-ttu-id="bea0d-563">完成以下步骤以更改[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]安装。</span><span class="sxs-lookup"><span data-stu-id="bea0d-563">Complete the following steps to change the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] installation.</span></span> <span data-ttu-id="bea0d-564">请确保你具有[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]安装之前您运行安装向导以修改[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]安装。</span><span class="sxs-lookup"><span data-stu-id="bea0d-564">Make sure you have the [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)] installed before you run the setup wizard to modify the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] installation.</span></span>  
  
 <span data-ttu-id="bea0d-565">你可以修改[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]安装在交互模式下 （安装程序向导），或在静默模式下 （命令行）。</span><span class="sxs-lookup"><span data-stu-id="bea0d-565">You can modify the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] installation in interactive mode (the setup wizard), or in silent mode (the command line).</span></span>
  
#### <a name="change-the-bap-installation-in-interactive-mode"></a><span data-ttu-id="bea0d-566">更改 BAP 安装在交互模式中</span><span class="sxs-lookup"><span data-stu-id="bea0d-566">Change the BAP installation in interactive mode</span></span>  
  
1.  <span data-ttu-id="bea0d-567">使用 BizTalk Server Administrators 组的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="bea0d-567">Sign in using an account that is a member of the BizTalk Server Administrators group.</span></span>  
  
2.  <span data-ttu-id="bea0d-568">在**程序和功能**，选择**卸载程序**。</span><span class="sxs-lookup"><span data-stu-id="bea0d-568">In **Programs and features**, select **Uninstall a program**.</span></span>  
  
3.  <span data-ttu-id="bea0d-569">右键单击**Microsoft BizTalk 适配器包**，然后选择**更改**。</span><span class="sxs-lookup"><span data-stu-id="bea0d-569">Right-click **Microsoft BizTalk Adapter Pack**, and then select **Change**.</span></span>  
  
4.  <span data-ttu-id="bea0d-570">在欢迎屏幕上，选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="bea0d-570">On the Welcome screen, select **Next**.</span></span>  
  
5.  <span data-ttu-id="bea0d-571">在**更改、 修复或删除安装**:</span><span class="sxs-lookup"><span data-stu-id="bea0d-571">In **Change, repair, or remove installation**:</span></span>  
  
    -   <span data-ttu-id="bea0d-572">若要选择你想要安装的组件，选择**更改**并转到步骤 6。</span><span class="sxs-lookup"><span data-stu-id="bea0d-572">To select the components you want to install, select **Change** and go to Step 6.</span></span>  
  
    -   <span data-ttu-id="bea0d-573">若要修复最新安装中的错误，选择**修复**并转到步骤 7。</span><span class="sxs-lookup"><span data-stu-id="bea0d-573">To repair errors in the most recent installation, select **Repair** and go to Step 7.</span></span>  
  
    -   <span data-ttu-id="bea0d-574">若要删除 Microsoft[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]从计算机上，选择**删除**，然后转到步骤 10。</span><span class="sxs-lookup"><span data-stu-id="bea0d-574">To remove Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] from the computer, select **Remove** and then go to Step 10.</span></span>  
  
6.  <span data-ttu-id="bea0d-575">如果你选择要修改安装：</span><span class="sxs-lookup"><span data-stu-id="bea0d-575">If you chose to modify the installation:</span></span>  
  
    -   <span data-ttu-id="bea0d-576">展开**Microsoft BizTalk 适配器包**节点，以选择要安装的基的适配器和 / 或.NET Framework 数据提供程序。</span><span class="sxs-lookup"><span data-stu-id="bea0d-576">Expand the **Microsoft BizTalk Adapter Pack** node to choose to install the base adapters, the .NET Framework Data Providers, or both.</span></span>  
  
    -   <span data-ttu-id="bea0d-577">展开**基适配器**节点，以选择安装所有适配器或特定的适配器。</span><span class="sxs-lookup"><span data-stu-id="bea0d-577">Expand the **Base Adapters** node to choose to install all the adapters or specific adapters.</span></span>  
  
    -   <span data-ttu-id="bea0d-578">展开**ADO 提供程序**节点，以选择安装所有提供程序或特定的提供程序安装。</span><span class="sxs-lookup"><span data-stu-id="bea0d-578">Expand the **ADO Providers** node to choose to install all the providers or specific providers.</span></span>  
  
    -   <span data-ttu-id="bea0d-579">选择“下一步” 。</span><span class="sxs-lookup"><span data-stu-id="bea0d-579">Select **Next**.</span></span>  
  
    -   <span data-ttu-id="bea0d-580">选择**更改**，然后选择**完成**。</span><span class="sxs-lookup"><span data-stu-id="bea0d-580">Select **Change**, and then select **Finish**.</span></span>  
  
7.  <span data-ttu-id="bea0d-581">如果你选择在修复安装，**准备好修复 Microsoft BizTalk 适配器包**对话框中，选择**修复**。</span><span class="sxs-lookup"><span data-stu-id="bea0d-581">If you chose to repair the installation, in the **Ready to repair Microsoft BizTalk Adapter Pack** dialog box, select **Repair**.</span></span> <span data-ttu-id="bea0d-582">启动向导，修复安装。</span><span class="sxs-lookup"><span data-stu-id="bea0d-582">The wizard starts repairing the installation.</span></span>  
  
8.  <span data-ttu-id="bea0d-583">如果需要，更改你的首选项有关选择加入的 CEIP，，然后选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="bea0d-583">If required, change your preferences regarding opting for CEIP, and then select **OK**.</span></span> 
  
9. <span data-ttu-id="bea0d-584">选择“完成”。</span><span class="sxs-lookup"><span data-stu-id="bea0d-584">Select **Finish**.</span></span>  
  
10. <span data-ttu-id="bea0d-585">如果您选择中删除适配器，**准备好删除 Microsoft BizTalk 适配器包**对话框中，选择**删除**，然后选择**完成**。</span><span class="sxs-lookup"><span data-stu-id="bea0d-585">If you chose to remove the adapters, in the **Ready to remove Microsoft BizTalk Adapter Pack** dialog box, select **Remove**, and then select **Finish**.</span></span>  
  
#### <a name="change-the-bap-installation-in-silent-mode"></a><span data-ttu-id="bea0d-586">更改在静默模式下 BAP 安装</span><span class="sxs-lookup"><span data-stu-id="bea0d-586">Change the BAP installation in silent mode</span></span>  
  
1.  <span data-ttu-id="bea0d-587">打开命令提示符，并转到根目录下的[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]安装程序。</span><span class="sxs-lookup"><span data-stu-id="bea0d-587">Open a command prompt, and go to the root directory of the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] installer.</span></span>  
  
2.  <span data-ttu-id="bea0d-588">运行如下命令：</span><span class="sxs-lookup"><span data-stu-id="bea0d-588">Run a command similar to the following:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bea0d-589">若要修改[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]在基于 x64 的平台上，在以下命令，以无提示模式安装替换`AdaptersSetup.msi`与`AdaptersSetup64.msi`。</span><span class="sxs-lookup"><span data-stu-id="bea0d-589">To modify the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] installation in a silent mode on an x64-based platform, in the following commands, replace `AdaptersSetup.msi` with `AdaptersSetup64.msi`.</span></span>  
  
    ```  
    msiexec /i AdaptersSetup.msi /qn REMOVE=DbFeature ADDLOCAL=SapBaseAdapterFeature  
    ```  
  
     <span data-ttu-id="bea0d-590">此命令删除[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]，并安装[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bea0d-590">This command removes the [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)], and installs the [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)].</span></span>  
  
     <span data-ttu-id="bea0d-591">通过使用不同的值`REMOVE`和`ADDLOCAL`属性，可以添加或删除特定的组件。</span><span class="sxs-lookup"><span data-stu-id="bea0d-591">By using different values for the `REMOVE` and `ADDLOCAL` properties, you can add or remove specific components.</span></span> <span data-ttu-id="bea0d-592">中的表是指[在无提示模式下安装 BizTalk 适配器包](#BKMK_SilentInst)（本主题中） 中有关你可以使用这些属性的值。</span><span class="sxs-lookup"><span data-stu-id="bea0d-592">Refer to the table in [Installing the BizTalk Adapter Pack in Silent Mode](#BKMK_SilentInst) (in this topic) for information about the values that you can use for these properties.</span></span>  
  
     <span data-ttu-id="bea0d-593">你还可以通过为 msiexec 命令的一部分使用 /f 选项来执行无提示的修复。</span><span class="sxs-lookup"><span data-stu-id="bea0d-593">You can also do a silent repair by using the /f option as part of the msiexec command.</span></span> <span data-ttu-id="bea0d-594">例如：</span><span class="sxs-lookup"><span data-stu-id="bea0d-594">For example:</span></span>  
  
    ```  
    msiexec /i AdaptersSetup.msi /qn /f  
    ```  
  
     <span data-ttu-id="bea0d-595">带 /f 选项，可以使用各种不同的组合。</span><span class="sxs-lookup"><span data-stu-id="bea0d-595">You can use various different combinations with the /f option.</span></span> <span data-ttu-id="bea0d-596">有关 msiexec 命令类型的详细信息`msiexec`上的命令行和按`ENTER`。</span><span class="sxs-lookup"><span data-stu-id="bea0d-596">For more information about the msiexec command type `msiexec` on the command line, and press `ENTER`.</span></span> <span data-ttu-id="bea0d-597">或转到[http://go.microsoft.com/fwlink/p/?LinkId=103199](http://go.microsoft.com/fwlink/p/?LinkId=103199)。</span><span class="sxs-lookup"><span data-stu-id="bea0d-597">Or go to [http://go.microsoft.com/fwlink/p/?LinkId=103199](http://go.microsoft.com/fwlink/p/?LinkId=103199).</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="bea0d-598">修改时[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]在静默模式下的安装，不能更改用于选择加入或退出 CEIP 首选项。</span><span class="sxs-lookup"><span data-stu-id="bea0d-598">While modifying the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] installation in the silent mode, you cannot change your preferences for opting in or out of CEIP.</span></span> <span data-ttu-id="bea0d-599">在过程中选择该安装将保持，即使你显式设置为 true 或 false 的 CEIP_OPTIN 首选项。</span><span class="sxs-lookup"><span data-stu-id="bea0d-599">The preferences you chose during the installation remains, even if you explicitly set the CEIP_OPTIN to true or false.</span></span>  
  
<a name="BKMK_Remove_Adap"></a>   
## <a name="removing-the-biztalk-adapter-pack"></a><span data-ttu-id="bea0d-600">删除 BizTalk 适配器包</span><span class="sxs-lookup"><span data-stu-id="bea0d-600">Removing the BizTalk Adapter Pack</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="bea0d-601">如果你在要使用的 tRFC 功能的 SQL Server 数据库中创建表[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]，你必须手动删除之前删除它们[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bea0d-601">If you created tables in the SQL Server database to work with the tRFC feature of the [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)], you must manually remove them before removing the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="bea0d-602">[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]安装将 SapAdapter DbScript Uninstall.sql 文件通常情况下的复制\<安装驱动器 >: files\microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bea0d-602">The [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] installation copies a SapAdapter-DbScript-Uninstall.sql file typically at \<installation drive>:\Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="bea0d-603">运行此文件，以删除你创建的表。</span><span class="sxs-lookup"><span data-stu-id="bea0d-603">Run this file to remove the tables you created.</span></span>  
  
<span data-ttu-id="bea0d-604">完成以下步骤以删除[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]从您的计算机。</span><span class="sxs-lookup"><span data-stu-id="bea0d-604">Complete the following steps to remove the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] from your computer.</span></span> <span data-ttu-id="bea0d-605">请确保你具有[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]安装之前您运行安装向导以删除适配器。</span><span class="sxs-lookup"><span data-stu-id="bea0d-605">Make sure you have the [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)] installed before you run the setup wizard to remove the adapters.</span></span>  
  
 <span data-ttu-id="bea0d-606">你可以删除[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]在交互模式 （安装程序向导） 中或在静默模式下 （命令行）。</span><span class="sxs-lookup"><span data-stu-id="bea0d-606">You can remove the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] in interactive mode (setup wizard), or in silent mode (command line).</span></span>
  
#### <a name="uninstall-the-biztalk-adapter-pack-in-interactive-mode"></a><span data-ttu-id="bea0d-607">卸载在交互模式中的 BizTalk 适配器包</span><span class="sxs-lookup"><span data-stu-id="bea0d-607">Uninstall the BizTalk Adapter Pack in interactive mode</span></span>  
  
1.  <span data-ttu-id="bea0d-608">在**程序和功能**，选择**卸载程序**。</span><span class="sxs-lookup"><span data-stu-id="bea0d-608">In **Programs and features**, select **Uninstall a program**.</span></span>  
  
2.  <span data-ttu-id="bea0d-609">右键单击**Microsoft BizTalk 适配器包**，然后选择**卸载**。</span><span class="sxs-lookup"><span data-stu-id="bea0d-609">Right-click **Microsoft BizTalk Adapter Pack**, and then select **Uninstall**.</span></span>  
  
#### <a name="uninstall-the-biztalk-adapter-pack-in-silent-mode"></a><span data-ttu-id="bea0d-610">卸载在静默模式下 BizTalk 适配器包</span><span class="sxs-lookup"><span data-stu-id="bea0d-610">Uninstall the BizTalk Adapter Pack in silent mode</span></span>  
  
1.  <span data-ttu-id="bea0d-611">打开命令提示符，并转到根目录下的[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]安装程序。</span><span class="sxs-lookup"><span data-stu-id="bea0d-611">Open a command prompt, and go to the root directory of the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] installer.</span></span>  
  
2.  <span data-ttu-id="bea0d-612">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="bea0d-612">Run the following command:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bea0d-613">若要删除[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]在静默模式下，在基于 x64 的平台上，在以下命令，将`AdaptersSetup.msi`与`AdaptersSetup64.msi`。</span><span class="sxs-lookup"><span data-stu-id="bea0d-613">To remove the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] in silent mode on an x64-based platform, in the following commands, replace `AdaptersSetup.msi` with `AdaptersSetup64.msi`.</span></span>  
  
    ```  
    msiexec /i AdaptersSetup.msi /qn REMOVE=DbFeature  
    ```  
  
     <span data-ttu-id="bea0d-614">此命令删除[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]从[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]安装。</span><span class="sxs-lookup"><span data-stu-id="bea0d-614">This command removes the [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)] from the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] installation.</span></span>  
  
     <span data-ttu-id="bea0d-615">通过提供不同的值`REMOVE`属性，您可以删除从特定组件[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]安装。</span><span class="sxs-lookup"><span data-stu-id="bea0d-615">By providing different values for the `REMOVE` property, you can remove specific components from the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] installation.</span></span> <span data-ttu-id="bea0d-616">中的表是指[在无提示模式下安装 BizTalk 适配器包](#BKMK_SilentInst)（本主题中） 中有关你可以使用此属性的值。</span><span class="sxs-lookup"><span data-stu-id="bea0d-616">Refer to the table in [Installing the BizTalk Adapter Pack in Silent Mode](#BKMK_SilentInst) (in this topic) for information about the values that you can use for this property.</span></span>  
  
     <span data-ttu-id="bea0d-617">若要完全删除[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]，执行以下命令：</span><span class="sxs-lookup"><span data-stu-id="bea0d-617">To completely remove the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)], execute the following command:</span></span>  
  
    ```  
    msiexec /x AdaptersSetup.msi /qn  
    ```  
  
     <span data-ttu-id="bea0d-618">有关 msiexec 命令类型的详细信息`msiexec`上的命令行和按`ENTER`。</span><span class="sxs-lookup"><span data-stu-id="bea0d-618">For more information about the msiexec command type `msiexec` on the command line, and press `ENTER`.</span></span> <span data-ttu-id="bea0d-619">或转到[http://go.microsoft.com/fwlink/p/?LinkId=103199](http://go.microsoft.com/fwlink/p/?LinkId=103199)。</span><span class="sxs-lookup"><span data-stu-id="bea0d-619">Or go to [http://go.microsoft.com/fwlink/p/?LinkId=103199](http://go.microsoft.com/fwlink/p/?LinkId=103199).</span></span>
  
<a name="BKMK_PostRemove"></a>   
### <a name="after-removing-the-biztalk-adapter-pack"></a><span data-ttu-id="bea0d-620">删除 BizTalk 适配器包后</span><span class="sxs-lookup"><span data-stu-id="bea0d-620">After removing the BizTalk Adapter Pack</span></span>  
 <span data-ttu-id="bea0d-621">你可能需要删除后执行以下步骤[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="bea0d-621">You may need to perform the following steps after removing the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="bea0d-622">删除适配器绑定或.NET Framework 数据提供程序在注册时，如果安装向导未能完成此操作</span><span class="sxs-lookup"><span data-stu-id="bea0d-622">Remove the adapter bindings or the .NET Framework Data Provider registration, if the setup wizard failed to do so</span></span>
  
-   <span data-ttu-id="bea0d-623">删除自定义的 Rfc 中，如果你选择安装[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bea0d-623">Remove the custom RFCs, if you chose to install the [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]</span></span>
  
<a name="BKMK_Remove_Binding"></a>   
#### <a name="remove-the-bindings-or-the-net-framework-data-provider-registration"></a><span data-ttu-id="bea0d-624">删除绑定或.NET Framework 数据提供程序注册</span><span class="sxs-lookup"><span data-stu-id="bea0d-624">Remove the bindings or the .NET Framework Data Provider registration</span></span>  
 <span data-ttu-id="bea0d-625">完成这些步骤*仅*如果安装向导无法从 machine.config 文件中删除适配器绑定或.NET Framework 数据提供程序注册。</span><span class="sxs-lookup"><span data-stu-id="bea0d-625">Complete these steps *only* if the setup wizard fails to remove the adapter bindings or .NET Framework Data Provider registration from the machine.config file.</span></span>  
  
###### <a name="remove-the-adapter-bindings-or-net-framework-data-provider-registration"></a><span data-ttu-id="bea0d-626">删除适配器绑定或.NET Framework 数据提供程序注册</span><span class="sxs-lookup"><span data-stu-id="bea0d-626">Remove the adapter bindings or .NET Framework Data Provider registration</span></span>  
  
1.  <span data-ttu-id="bea0d-627">转到计算机上的 machine.config 文件。</span><span class="sxs-lookup"><span data-stu-id="bea0d-627">Go to the machine.config file on the computer.</span></span> <span data-ttu-id="bea0d-628">例如，在 32 位平台上，machine.config 位于下\<系统驱动器 >: \WINDOWS\Microsoft.NET\Framework\\< 版本\>\CONFIG。</span><span class="sxs-lookup"><span data-stu-id="bea0d-628">For example, on a 32-bit platform, the machine.config is available under \<system drive>:\WINDOWS\Microsoft.NET\Framework\\<version\>\CONFIG.</span></span>  
  
2.  <span data-ttu-id="bea0d-629">打开使用文本编辑器的文件。</span><span class="sxs-lookup"><span data-stu-id="bea0d-629">Open the file using a text editor.</span></span>  
  
3.  <span data-ttu-id="bea0d-630">删除适配器绑定注册：</span><span class="sxs-lookup"><span data-stu-id="bea0d-630">Remove the adapter binding registration:</span></span>  
  
    1.  <span data-ttu-id="bea0d-631">搜索`system.serviceModel`元素，并删除以下从元素：</span><span class="sxs-lookup"><span data-stu-id="bea0d-631">Search for the `system.serviceModel` element, and remove the following from under the element:</span></span>  
  
        ```  
        <client>  
          <endpoint binding="sapBinding" contract="IMetadataExchange" name="sap" />  
          <endpoint binding="siebelBinding" contract="IMetadataExchange" name="siebel" />  
          <endpoint binding="oracleDBBinding" contract="IMetadataExchange" name="oracleDb" />  
          <endpoint binding="OracleEBSBinding" contract="IMetadataExchange" name="oracleEBS" />  
          <endpoint binding="sqlBinding" contract="IMetadataExchange" name="mssql" />  
        </client>  
  
        ```  
  
    2.  <span data-ttu-id="bea0d-632">搜索`bindingElementExtensions`system.serviceModel\extensions 下的元素。</span><span class="sxs-lookup"><span data-stu-id="bea0d-632">Search for the `bindingElementExtensions` element under system.serviceModel\extensions.</span></span>  
  
    3.  <span data-ttu-id="bea0d-633">删除以下各节下的`bindingElementExtensions`节点，具体取决于可用的适配器绑定。</span><span class="sxs-lookup"><span data-stu-id="bea0d-633">Remove the following sections under the `bindingElementExtensions` node, depending on the available adapter binding.</span></span> <span data-ttu-id="bea0d-634">如果安装向导删除任何失败，则必须删除所有绑定。</span><span class="sxs-lookup"><span data-stu-id="bea0d-634">You must remove all the bindings if the setup wizard fails to remove any.</span></span>  
  
         <span data-ttu-id="bea0d-635">有关[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]，删除：</span><span class="sxs-lookup"><span data-stu-id="bea0d-635">For [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)], remove:</span></span>  
  
        ```  
        <add name="sapAdapter" type="Microsoft.Adapters.SAP.SAPAdapterExtensionElement,Microsoft.Adapters.SAP, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         <span data-ttu-id="bea0d-636">有关[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]，删除：</span><span class="sxs-lookup"><span data-stu-id="bea0d-636">For [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)], remove:</span></span>  
  
        ```  
        <add name="siebelAdapter" type="Microsoft.Adapters.Siebel.SiebelAdapterExtensionElement,Microsoft.Adapters.Siebel, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         <span data-ttu-id="bea0d-637">有关[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]，删除：</span><span class="sxs-lookup"><span data-stu-id="bea0d-637">For [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)], remove:</span></span>  
  
        ```  
        <add name="oracleDBAdapter" type="Microsoft.Adapters.OracleDB.OracleDBAdapterExtensionElement,Microsoft.Adapters.OracleDB, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         <span data-ttu-id="bea0d-638">有关[!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)]，删除：</span><span class="sxs-lookup"><span data-stu-id="bea0d-638">For [!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)], remove:</span></span>  
  
        ```  
        <add name="OracleEBSAdapter" type="Microsoft.Adapters.OracleEBS.OracleEBSBindingElementExtensionElement, Microsoft.Adapters.OracleEBS, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         <span data-ttu-id="bea0d-639">有关[!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]，删除：</span><span class="sxs-lookup"><span data-stu-id="bea0d-639">For [!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)], remove:</span></span>  
  
        ```  
        <add name="sqlAdapter" type="Microsoft.Adapters.Sql.SqlAdapterBindingElementExtensionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
    4.  <span data-ttu-id="bea0d-640">搜索`bindingExtensions`system.serviceModel\extensions 下的元素。</span><span class="sxs-lookup"><span data-stu-id="bea0d-640">Search for the `bindingExtensions` element under system.serviceModel\extensions.</span></span>  
  
    5.  <span data-ttu-id="bea0d-641">删除以下各节下的`bindingExtensions`节点，具体取决于可用的适配器绑定。</span><span class="sxs-lookup"><span data-stu-id="bea0d-641">Remove the following sections under the `bindingExtensions` node, depending on the available adapter binding.</span></span> <span data-ttu-id="bea0d-642">如果安装向导删除任何失败，则必须删除所有绑定。</span><span class="sxs-lookup"><span data-stu-id="bea0d-642">You must remove all the bindings if the setup wizard fails to remove any.</span></span>  
  
         <span data-ttu-id="bea0d-643">有关[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]，删除：</span><span class="sxs-lookup"><span data-stu-id="bea0d-643">For [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)], remove:</span></span>  
  
        ```  
        <add name="sapBinding" type="Microsoft.Adapters.SAP.SAPAdapterBindingSection,Microsoft.Adapters.SAP, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         <span data-ttu-id="bea0d-644">有关[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]，删除：</span><span class="sxs-lookup"><span data-stu-id="bea0d-644">For [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)], remove:</span></span>  
  
        ```  
        <add name="siebelBinding" type="Microsoft.Adapters.Siebel.SiebelAdapterBindingSection,Microsoft.Adapters.Siebel, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         <span data-ttu-id="bea0d-645">有关[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]，删除：</span><span class="sxs-lookup"><span data-stu-id="bea0d-645">For [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)], remove:</span></span>  
  
        ```  
        <add name="oracleDBBinding" type="Microsoft.Adapters.OracleDB.OracleDBAdapterBindingSection,Microsoft.Adapters.OracleDB, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         <span data-ttu-id="bea0d-646">有关[!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)]，删除：</span><span class="sxs-lookup"><span data-stu-id="bea0d-646">For [!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)], remove:</span></span>  
  
        ```  
        <add name="OracleEBSBinding" type="Microsoft.Adapters.OracleEBS.OracleEBSBindingCollectionElement, Microsoft.Adapters.OracleEBS, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         <span data-ttu-id="bea0d-647">有关[!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]，删除：</span><span class="sxs-lookup"><span data-stu-id="bea0d-647">For [!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)], remove:</span></span>  
  
        ```  
        <add name="sqlBinding" type="Microsoft.Adapters.Sql.SqlAdapterBindingCollectionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
4.  <span data-ttu-id="bea0d-648">删除.NET Framework 数据提供程序注册：</span><span class="sxs-lookup"><span data-stu-id="bea0d-648">Remove the .NET Framework Data Provider registration:</span></span>  
  
    -   <span data-ttu-id="bea0d-649">搜索`DbProviderFactories`system.data 节点下的元素。</span><span class="sxs-lookup"><span data-stu-id="bea0d-649">Search for the `DbProviderFactories` element under the system.data node.</span></span>  
  
    -   <span data-ttu-id="bea0d-650">查找仍有注册.NET Framework 数据提供程序。</span><span class="sxs-lookup"><span data-stu-id="bea0d-650">Look for the .NET Framework Data Providers that are still registered.</span></span> <span data-ttu-id="bea0d-651">删除以下各节下的`DbProviderFactories`节点，具体取决于现有的.NET Framework 数据提供程序。</span><span class="sxs-lookup"><span data-stu-id="bea0d-651">Remove the following sections under the `DbProviderFactories` node, depending on the existing .NET Framework Data Providers.</span></span> <span data-ttu-id="bea0d-652">如果它们存在，则必须删除所有提供程序。</span><span class="sxs-lookup"><span data-stu-id="bea0d-652">You must remove all the providers if they exist.</span></span>  
  
         <span data-ttu-id="bea0d-653">有关[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]，删除：</span><span class="sxs-lookup"><span data-stu-id="bea0d-653">For [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)], remove:</span></span>  
  
        ```  
        <add name="SAPClient Data Provider" invariant="Microsoft.Data.SAPClient"   
            description=".NET Framework Data Provider for mySAP Business Suite"    type="Microsoft.Data.SAPClient.SAPClientFactory,Microsoft.Data.SAPClient, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         <span data-ttu-id="bea0d-654">有关[!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]，删除：</span><span class="sxs-lookup"><span data-stu-id="bea0d-654">For [!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)], remove:</span></span>  
  
        ```  
        <add name="SiebelClient Data Provider" invariant="Microsoft.Data.SiebelClient"  
            description=".NET Framework Data Provider for Siebel eBusiness Applications"  
            type="Microsoft.Data.SiebelClient.SiebelProviderFactory,Microsoft.Data.SiebelClient, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
5.  <span data-ttu-id="bea0d-655">保存并关闭 machine.config 文件。</span><span class="sxs-lookup"><span data-stu-id="bea0d-655">Save and close the machine.config file.</span></span>  
  
<a name="BKMK_Remove_SAP_Pro"></a>   
#### <a name="remove-the-custom-rfcs"></a><span data-ttu-id="bea0d-656">删除自定义的 Rfc</span><span class="sxs-lookup"><span data-stu-id="bea0d-656">Remove the custom RFCs</span></span>  
<span data-ttu-id="bea0d-657">完成此步骤以删除 SAP 系统中安装了自定义 Rfc。</span><span class="sxs-lookup"><span data-stu-id="bea0d-657">Complete this step to remove the custom RFCs that you installed in the SAP system.</span></span> <span data-ttu-id="bea0d-658">请参阅[安装或删除自定义的 Rfc](../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)。</span><span class="sxs-lookup"><span data-stu-id="bea0d-658">See [Install or remove custom RFCs](../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md).</span></span>  
  
## <a name="troubleshoot-biztalk-adapter-pack-installation"></a><span data-ttu-id="bea0d-659">BizTalk 适配器包安装进行故障排除</span><span class="sxs-lookup"><span data-stu-id="bea0d-659">Troubleshoot BizTalk Adapter Pack installation</span></span>  
 <span data-ttu-id="bea0d-660">以下是在安装时，你可能面临一些问题[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bea0d-660">Following are some issues that you might face when installing [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="bea0d-661">有关安装相关的问题的完整列表，请参阅**疑难解答**为每个适配器的主题。</span><span class="sxs-lookup"><span data-stu-id="bea0d-661">For a comprehensive list of installation-related issues, refer to **Troublehsooting** topics for each adapter.</span></span>  
  
-   <span data-ttu-id="bea0d-662">**在 64 位计算机上的运行安装程序可能会访问架构文件时将引发错误**</span><span class="sxs-lookup"><span data-stu-id="bea0d-662">**Running setup on a 64-bit computer might throw an error while accessing schema file**</span></span>  
  
     <span data-ttu-id="bea0d-663">[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]安装程序在访问时引发错误 **Microsoft.Adapters。*\<AdapterName >*_schema.xml** 文件，但与适配器安装继续进行。</span><span class="sxs-lookup"><span data-stu-id="bea0d-663">The [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] setup throws an error while accessing the **Microsoft.Adapters.*\<AdapterName>*_schema.xml** file, but proceeds with the adapter installation.</span></span>  
  
     <span data-ttu-id="bea0d-664">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="bea0d-664">**Cause**</span></span>  
  
     <span data-ttu-id="bea0d-665">如果 32 位和 64 位版本的[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]安装在同一计算机上使用两个目标架构文件是相同。</span><span class="sxs-lookup"><span data-stu-id="bea0d-665">If both 32-bit and 64-bit versions of the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] are installed on the same computer, the target schema file used by both is the same.</span></span> <span data-ttu-id="bea0d-666">因此，该文件安装 32 位[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]可能正在使用 IIS 时 64 位安装程序会尝试访问它。</span><span class="sxs-lookup"><span data-stu-id="bea0d-666">As a result, the file installed by the 32-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] might be in use by IIS when the 64-bit installer tries to access it.</span></span>  
  
     <span data-ttu-id="bea0d-667">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="bea0d-667">**Resolution**</span></span>  
  
     <span data-ttu-id="bea0d-668">手动复制 **Microsoft.Adapters。*\<AdapterName >*_schema.xml** 文件从`C:\Program Files\Microsoft BizTalk Adapter Pack(x64)\IIS Schemas`"到`C:\Windows\System32\inetsrv\config\schema`。</span><span class="sxs-lookup"><span data-stu-id="bea0d-668">Manually copy the **Microsoft.Adapters.*\<AdapterName>*_schema.xml** file from `C:\Program Files\Microsoft BizTalk Adapter Pack(x64)\IIS Schemas`" to `C:\Windows\System32\inetsrv\config\schema`.</span></span>  