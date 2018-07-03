---
title: 发布的 BizTalk 适配器包 2016年的安装步骤 |Microsoft Docs
description: 步骤完成后安装 BAP 2016，包括将适配器添加到 BizTalk 管理、 Oracle、 更新和注册适配器绑定。
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b8946bfe-92bb-470d-bec4-9bc3a07ce0d2
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 43a454e1e6f1dc65d8a2e2c5493aacf9375374b2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997374"
---
# <a name="post-installation-steps-for-biztalk-adapter-pack-2016"></a><span data-ttu-id="0dd5a-103">BizTalk 适配器包 2016年的安装后步骤</span><span class="sxs-lookup"><span data-stu-id="0dd5a-103">Post installation steps for BizTalk Adapter Pack 2016</span></span>
<span data-ttu-id="0dd5a-104">在安装后[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]，有一些安装后步骤。</span><span class="sxs-lookup"><span data-stu-id="0dd5a-104">After you install the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)], there are some post-installation steps.</span></span> <span data-ttu-id="0dd5a-105">本主题列出了这些步骤。</span><span class="sxs-lookup"><span data-stu-id="0dd5a-105">This topic lists these steps.</span></span>   

## <a name="add-the-adapter-to-biztalk-administration"></a><span data-ttu-id="0dd5a-106">将适配器添加到 BizTalk 管理</span><span class="sxs-lookup"><span data-stu-id="0dd5a-106">Add the adapter to BizTalk Administration</span></span>

1. <span data-ttu-id="0dd5a-107">打开[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="0dd5a-107">Open the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

2. <span data-ttu-id="0dd5a-108">展开**BizTalk 组**，展开**平台设置**，然后选择**适配器**。</span><span class="sxs-lookup"><span data-stu-id="0dd5a-108">Expand the **BizTalk Group**, expand **Platform Settings**, and then select **Adapters**.</span></span>  

3. <span data-ttu-id="0dd5a-109">右键单击**适配器**，选择**新建**，然后选择**适配器**。</span><span class="sxs-lookup"><span data-stu-id="0dd5a-109">Right-click **Adapters**, select **New**, and select **Adapter**.</span></span>  

    <span data-ttu-id="0dd5a-110">![将适配器添加](../adapters-and-accelerators/media/c9610d42-8465-4099-b403-87df6dcd0d99.gif "c9610d42-8465-4099-b403-87df6dcd0d99")</span><span class="sxs-lookup"><span data-stu-id="0dd5a-110">![Add an adapter](../adapters-and-accelerators/media/c9610d42-8465-4099-b403-87df6dcd0d99.gif "c9610d42-8465-4099-b403-87df6dcd0d99")</span></span>  

4. <span data-ttu-id="0dd5a-111">在中**适配器属性**，并从下拉列表中，选择一个适配器，如**WCF SAP**，然后输入一个名称，例如**WCF SAP**。</span><span class="sxs-lookup"><span data-stu-id="0dd5a-111">In the **Adapter Properties**, select an adapter from the drop-down list, such as **WCF-SAP**, and then enter a name, such as **WCF-SAP**.</span></span>  

    <span data-ttu-id="0dd5a-112">![将 SAP 适配器添加到 BizTalk](../adapters-and-accelerators/media/a1235b38-ab93-4233-924d-42710540b951.gif "a1235b38-ab93-4233-924d-42710540b951")</span><span class="sxs-lookup"><span data-stu-id="0dd5a-112">![Add SAP Adapter to BizTalk](../adapters-and-accelerators/media/a1235b38-ab93-4233-924d-42710540b951.gif "a1235b38-ab93-4233-924d-42710540b951")</span></span>  

5. <span data-ttu-id="0dd5a-113">选择“确定”。</span><span class="sxs-lookup"><span data-stu-id="0dd5a-113">Select **OK**.</span></span>  

## <a name="use-a-newer-oracledataaccessdll-version"></a><span data-ttu-id="0dd5a-114">使用较新的 Oracle.DataAccess.dll 版本</span><span class="sxs-lookup"><span data-stu-id="0dd5a-114">Use a newer Oracle.DataAccess.dll version</span></span>  

<span data-ttu-id="0dd5a-115">在配置要使用 Wcf-oracledb 适配器或使用 Visual Studio 使用生成的适配器的端口时，显示一条消息，适配器需要 Oracle.DataAccess.dll 版本 2.111.7.0。</span><span class="sxs-lookup"><span data-stu-id="0dd5a-115">When you configure a port to use the WCF-OracleDB adapter or use Visual Studio to consume a generated adapter, a message displays that the adapter needs Oracle.DataAccess.dll version 2.111.7.0.</span></span> <span data-ttu-id="0dd5a-116">若要解决此消息，请安装受支持的 Oracle.DataAccess.dll 版本 (请参阅[受支持版本列表](https://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx))，然后更新`bindingRedirect`元素在 OracleDB 配置文件中使用以下步骤：</span><span class="sxs-lookup"><span data-stu-id="0dd5a-116">To resolve this message, install a supported Oracle.DataAccess.dll version (see [supported version list](https://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)), and then update the `bindingRedirect` element in the OracleDB configuration file using the following steps:</span></span>  

1.  <span data-ttu-id="0dd5a-117">在 BizTalk 服务器上，请转到以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="0dd5a-117">On the BizTalk Server, go to the following folders:</span></span>  

     <span data-ttu-id="0dd5a-118">*驱动器*: \Program Files\Microsoft BizTalk Adapter Pack (x64) \bin</span><span class="sxs-lookup"><span data-stu-id="0dd5a-118">*drive*:\Program Files\Microsoft BizTalk Adapter Pack(x64)\bin</span></span>  

     <span data-ttu-id="0dd5a-119">*驱动器*: \Program 文件 (x86) \Microsoft BizTalk Adapter Pack\bin</span><span class="sxs-lookup"><span data-stu-id="0dd5a-119">*drive*:\Program Files (x86)\Microsoft BizTalk Adapter Pack\bin</span></span>  

2.  <span data-ttu-id="0dd5a-120">打开 Microsoft.Adapters.OracleDB.config 文件。</span><span class="sxs-lookup"><span data-stu-id="0dd5a-120">Open the Microsoft.Adapters.OracleDB.config file.</span></span>  

3.  <span data-ttu-id="0dd5a-121">找到的以下部分，然后复制/粘贴以下：</span><span class="sxs-lookup"><span data-stu-id="0dd5a-121">Find the following section, and then copy/paste the following:</span></span>  

    ```  
    <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
              <dependentAssembly>  
                        <assemblyIdentity name="Oracle.DataAccess" publicKeyToken="89b483f429c47342" culture="neutral" />  
                        <bindingRedirect oldVersion="2.111.7.00" newVersion="2.112.1.00"/>  
              </dependentAssembly>  
    </assemblyBinding>  

    ```  

    > [!NOTE]
    >  <span data-ttu-id="0dd5a-122">在此示例中，我们将设置*newVersion* 2.112.1.00 到。</span><span class="sxs-lookup"><span data-stu-id="0dd5a-122">In this example, we set *newVersion* to 2.112.1.00.</span></span> <span data-ttu-id="0dd5a-123">将此值设置为已安装的版本。</span><span class="sxs-lookup"><span data-stu-id="0dd5a-123">Set this value to the version you have installed.</span></span>  

> [!IMPORTANT]
> - <span data-ttu-id="0dd5a-124">如果此组中有多个 BizTalk Server，请在组中的所有 BizTalk 服务器上进行此更改。</span><span class="sxs-lookup"><span data-stu-id="0dd5a-124">If there are multiple BizTalk Servers in this group, make this change on all the BizTalk servers in the group.</span></span>  
> - <span data-ttu-id="0dd5a-125">*NewVersion*值需要更新基于 Oracle.DataAccess.dll 文件在计算机上安装的版本。</span><span class="sxs-lookup"><span data-stu-id="0dd5a-125">The *newVersion* value needs to be updated based on the version of the Oracle.DataAccess.dll file installed on the computer.</span></span>  <span data-ttu-id="0dd5a-126">包含从 Oracle 安装 Oracle 客户端 Oracle.DataAccess.dll。</span><span class="sxs-lookup"><span data-stu-id="0dd5a-126">Oracle.DataAccess.dll is included with the Oracle Client you install from Oracle.</span></span>  <span data-ttu-id="0dd5a-127">您只需安装的 Oracle 客户端版本[支持的 BizTalk 适配器包](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)。</span><span class="sxs-lookup"><span data-stu-id="0dd5a-127">You must only install an Oracle Client version that is [supported by the BizTalk Adapter Pack](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx).</span></span>  

## <a name="create-sql-server-database-objects-sap-adapter-only"></a><span data-ttu-id="0dd5a-128">创建 SQL Server 数据库对象 （仅适用于 SAP 适配器）</span><span class="sxs-lookup"><span data-stu-id="0dd5a-128">Create SQL Server Database objects (SAP adapter only)</span></span>  
 <span data-ttu-id="0dd5a-129">若要调用 Trfc SAP 系统中，运行*SapAdapter DbScript Install.sql* SQL 脚本。</span><span class="sxs-lookup"><span data-stu-id="0dd5a-129">To invoke tRFCs in an SAP system, run the *SapAdapter-DbScript-Install.sql* SQL script.</span></span> <span data-ttu-id="0dd5a-130">此脚本安装使用[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]安装，并在 SQL Server 中创建数据库对象。</span><span class="sxs-lookup"><span data-stu-id="0dd5a-130">This script is installed with the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] installation, and creates database objects in SQL Server.</span></span> <span data-ttu-id="0dd5a-131">该脚本通常安装在*\<安装驱动器\>: \Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]* 。</span><span class="sxs-lookup"><span data-stu-id="0dd5a-131">The script is typically installed at *\<installation drive\>:\Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]*.</span></span> <span data-ttu-id="0dd5a-132">只要使用的适配器来调用 Trfc 时输入该数据库名称，可以针对任何 SQL Server 数据库，运行此脚本。</span><span class="sxs-lookup"><span data-stu-id="0dd5a-132">You can run this script against any SQL Server database, as long as you enter that database name while using the adapter to invoke tRFCs.</span></span>

## <a name="register-the-adapter-bindings"></a><span data-ttu-id="0dd5a-133">注册适配器绑定</span><span class="sxs-lookup"><span data-stu-id="0dd5a-133">Register the adapter bindings</span></span>
<span data-ttu-id="0dd5a-134">期间[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]安装，安装向导可能无法注册适配器绑定或.NET Framework Data Provider for mySAP Business Suite。</span><span class="sxs-lookup"><span data-stu-id="0dd5a-134">During the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] installation, the setup wizard may fail to register the adapter bindings or the .NET Framework Data Provider for mySAP Business Suite.</span></span> <span data-ttu-id="0dd5a-135">和安装程序继续执行适配器安装。</span><span class="sxs-lookup"><span data-stu-id="0dd5a-135">And the setup proceeds with the adapter installation.</span></span> <span data-ttu-id="0dd5a-136">这可能由 Windows Communication Foundation (WCF) 安装过程中，[!INCLUDE[afproductnamelong](../includes/afproductnamelong-md.md)]安装或被损坏的 machine.config 文件。</span><span class="sxs-lookup"><span data-stu-id="0dd5a-136">This may be caused by the Windows Communication Foundation (WCF) installation, the [!INCLUDE[afproductnamelong](../includes/afproductnamelong-md.md)] installation, or the machine.config file being corrupt.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="0dd5a-137">完成以下步骤*仅*如果安装向导无法在 machine.config 文件中注册的适配器的绑定或.NET Framework 数据提供程序。</span><span class="sxs-lookup"><span data-stu-id="0dd5a-137">Complete the following steps *only* if the setup wizard fails to register the adapter bindings, or .NET Framework Data Providers in the machine.config file.</span></span>  

1. <span data-ttu-id="0dd5a-138">请转到计算机上的 machine.config 文件。</span><span class="sxs-lookup"><span data-stu-id="0dd5a-138">Go to the machine.config file on the computer.</span></span> <span data-ttu-id="0dd5a-139">例如，在 32 位平台上，在 machine.config 位于下*\<系统驱动器\>: \WINDOWS\Microsoft.NET\Framework\\< 版本\>\CONFIG*。</span><span class="sxs-lookup"><span data-stu-id="0dd5a-139">For example, on a 32-bit platform, the machine.config is available under *\<system drive\>:\WINDOWS\Microsoft.NET\Framework\\<version\>\CONFIG*.</span></span>  

2. <span data-ttu-id="0dd5a-140">打开文件使用文本编辑器。</span><span class="sxs-lookup"><span data-stu-id="0dd5a-140">Open the file using a text editor.</span></span>  

3. <span data-ttu-id="0dd5a-141">注册适配器绑定：</span><span class="sxs-lookup"><span data-stu-id="0dd5a-141">Register the adapter bindings:</span></span>  

   1. <span data-ttu-id="0dd5a-142">搜索`system.serviceModel`元素，并添加其下的以下：</span><span class="sxs-lookup"><span data-stu-id="0dd5a-142">Search for the `system.serviceModel` element, and add the following under it:</span></span>  

      ```  
      <client>  
        <endpoint binding="sapBinding" contract="IMetadataExchange" name="sap" />  
        <endpoint binding="siebelBinding" contract="IMetadataExchange" name="siebel" />  
        <endpoint binding="oracleDBBinding" contract="IMetadataExchange" name="oracleDb" />  
        <endpoint binding="oracleEBSBinding" contract="IMetadataExchange" name="oracleEBS" />  
        <endpoint binding="sqlBinding" contract="IMetadataExchange" name="mssql" />  
      </client>  
      ```  

   2. <span data-ttu-id="0dd5a-143">搜索`bindingElementExtensions`system.serviceModel\extensions 下的元素。</span><span class="sxs-lookup"><span data-stu-id="0dd5a-143">Search for the `bindingElementExtensions` element under system.serviceModel\extensions.</span></span>  

   3. <span data-ttu-id="0dd5a-144">查找缺失的适配器绑定。</span><span class="sxs-lookup"><span data-stu-id="0dd5a-144">Look for the missing adapter binding.</span></span> <span data-ttu-id="0dd5a-145">添加以下各节下的`bindingElementExtensions`节点，具体取决于缺少的适配器绑定。</span><span class="sxs-lookup"><span data-stu-id="0dd5a-145">Add the following sections under the `bindingElementExtensions` node, depending on the missing adapter binding.</span></span> <span data-ttu-id="0dd5a-146">如果安装向导无法注册任何，则必须注册的所有绑定。</span><span class="sxs-lookup"><span data-stu-id="0dd5a-146">You must register all the bindings if the setup wizard fails to register any.</span></span>  

       <span data-ttu-id="0dd5a-147">有关[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]，添加：</span><span class="sxs-lookup"><span data-stu-id="0dd5a-147">For the [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)], add:</span></span>  

      ```  
      <add name="sapAdapter" type="Microsoft.Adapters.SAP.SAPAdapterExtensionElement,Microsoft.Adapters.SAP, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

       <span data-ttu-id="0dd5a-148">有关[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]，添加：</span><span class="sxs-lookup"><span data-stu-id="0dd5a-148">For the [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)], add:</span></span>  

      ```  
      <add name="siebelAdapter" type="Microsoft.Adapters.Siebel.SiebelAdapterExtensionElement,Microsoft.Adapters.Siebel, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

       <span data-ttu-id="0dd5a-149">有关[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]，添加：</span><span class="sxs-lookup"><span data-stu-id="0dd5a-149">For the [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)], add:</span></span>  

      ```  
      <add name="oracleDBAdapter" type="Microsoft.Adapters.OracleDB.OracleDBAdapterExtensionElement,Microsoft.Adapters.OracleDB, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

       <span data-ttu-id="0dd5a-150">有关[!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)]，添加：</span><span class="sxs-lookup"><span data-stu-id="0dd5a-150">For the [!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)], add:</span></span>  

      ```  
      <add name="OracleEBSAdapter" type="Microsoft.Adapters.OracleEBS.OracleEBSBindingElementExtensionElement, Microsoft.Adapters.OracleEBS, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

       <span data-ttu-id="0dd5a-151">有关[!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]，添加：</span><span class="sxs-lookup"><span data-stu-id="0dd5a-151">For the [!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)], add:</span></span>  

      ```  
      <add name="sqlAdapter" type="Microsoft.Adapters.Sql.SqlAdapterBindingElementExtensionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

   4. <span data-ttu-id="0dd5a-152">搜索`bindingExtensions`system.serviceModel\extensions 下的元素。</span><span class="sxs-lookup"><span data-stu-id="0dd5a-152">Search for the `bindingExtensions` element under system.serviceModel\extensions.</span></span>  

   5. <span data-ttu-id="0dd5a-153">查找缺失的适配器绑定。</span><span class="sxs-lookup"><span data-stu-id="0dd5a-153">Look for the missing adapter binding.</span></span> <span data-ttu-id="0dd5a-154">添加以下各节下的`bindingExtensions`节点，具体取决于缺少的适配器绑定。</span><span class="sxs-lookup"><span data-stu-id="0dd5a-154">Add the following sections under the `bindingExtensions` node, depending on the missing adapter binding.</span></span> <span data-ttu-id="0dd5a-155">如果安装向导无法注册任何，则必须注册的所有绑定。</span><span class="sxs-lookup"><span data-stu-id="0dd5a-155">You must register all the bindings if the setup wizard fails to register any.</span></span>  

       <span data-ttu-id="0dd5a-156">有关[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]，添加：</span><span class="sxs-lookup"><span data-stu-id="0dd5a-156">For [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)], add:</span></span>  

      ```  
      <add name="sapBinding" type="Microsoft.Adapters.SAP.SAPAdapterBindingSection,Microsoft.Adapters.SAP, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

       <span data-ttu-id="0dd5a-157">有关[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]，添加：</span><span class="sxs-lookup"><span data-stu-id="0dd5a-157">For [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)], add:</span></span>  

      ```  
      <add name="siebelBinding" type="Microsoft.Adapters.Siebel.SiebelAdapterBindingSection,Microsoft.Adapters.Siebel, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

       <span data-ttu-id="0dd5a-158">有关[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]，添加：</span><span class="sxs-lookup"><span data-stu-id="0dd5a-158">For [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)], add:</span></span>  

      ```  
      <add name="oracleDBBinding" type="Microsoft.Adapters.OracleDB.OracleDBAdapterBindingSection,Microsoft.Adapters.OracleDB, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

       <span data-ttu-id="0dd5a-159">有关[!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)]，添加：</span><span class="sxs-lookup"><span data-stu-id="0dd5a-159">For [!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)], add:</span></span>  

      ```  
      <add name="OracleEBSBinding" type="Microsoft.Adapters.OracleEBS.OracleEBSBindingCollectionElement, Microsoft.Adapters.OracleEBS,Microsoft.Adapters.OracleEBS, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

       <span data-ttu-id="0dd5a-160">有关[!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]，添加：</span><span class="sxs-lookup"><span data-stu-id="0dd5a-160">For [!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)], add:</span></span>  

      ```  
      <add name="sqlBinding" type="Microsoft.Adapters.Sql.SqlAdapterBindingCollectionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

   > [!NOTE]
   >  <span data-ttu-id="0dd5a-161">若要获取的公钥值，请参阅**确定公用密钥和版本**（在本主题中）。</span><span class="sxs-lookup"><span data-stu-id="0dd5a-161">To get the public key value, see **Determine the public key and version** (in this topic).</span></span>  

4. <span data-ttu-id="0dd5a-162">注册.NET Framework 数据提供程序：</span><span class="sxs-lookup"><span data-stu-id="0dd5a-162">Register the .NET Framework data providers:</span></span>  

   1. <span data-ttu-id="0dd5a-163">搜索`DbProviderFactories`system.data 节点下的元素。</span><span class="sxs-lookup"><span data-stu-id="0dd5a-163">Search for the `DbProviderFactories` element under the system.data node.</span></span>  

   2. <span data-ttu-id="0dd5a-164">查找缺少的.NET Framework 数据提供程序。</span><span class="sxs-lookup"><span data-stu-id="0dd5a-164">Look for the missing .NET Framework Data Providers.</span></span> <span data-ttu-id="0dd5a-165">添加以下各节下的`DbProviderFactories`节点，具体取决于缺失的提供程序。</span><span class="sxs-lookup"><span data-stu-id="0dd5a-165">Add the following sections under the `DbProviderFactories` node, depending on the missing provider.</span></span> <span data-ttu-id="0dd5a-166">如果安装向导无法注册任何，则必须注册的所有提供程序。</span><span class="sxs-lookup"><span data-stu-id="0dd5a-166">You must register all the providers if the setup wizard fails to register any.</span></span>  

       <span data-ttu-id="0dd5a-167">有关[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]，添加：</span><span class="sxs-lookup"><span data-stu-id="0dd5a-167">For the [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)], add:</span></span>  

      ```  
      <add name="SAPClient Data Provider" invariant="Microsoft.Data.SAPClient"   
          description=".NET Framework Data Provider for mySAP Business Suite"    type="Microsoft.Data.SAPClient.SAPClientFactory,Microsoft.Data.SAPClient, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

       <span data-ttu-id="0dd5a-168">有关[!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]，添加：</span><span class="sxs-lookup"><span data-stu-id="0dd5a-168">For the [!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)], add:</span></span>  

      ```  
      <add name="SiebelClient Data Provider" invariant="Microsoft.Data.SiebelClient"  
          description=".NET Framework Data Provider for Siebel eBusiness Applications"  
          type="Microsoft.Data.SiebelClient.SiebelProviderFactory,Microsoft.Data.SiebelClient, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

5. <span data-ttu-id="0dd5a-169">保存并关闭 machine.config 文件。</span><span class="sxs-lookup"><span data-stu-id="0dd5a-169">Save and close the machine.config file.</span></span>  

## <a name="determine-the-public-key-and-version"></a><span data-ttu-id="0dd5a-170">确定公用密钥和版本</span><span class="sxs-lookup"><span data-stu-id="0dd5a-170">Determine the public key and version</span></span>  
 <span data-ttu-id="0dd5a-171">完成以下步骤来确定公用密钥和适配器或.NET Framework 数据提供程序的版本。</span><span class="sxs-lookup"><span data-stu-id="0dd5a-171">Complete the following steps to determine the public key and version for an adapter or the .NET Framework Data Provider.</span></span>  

1. <span data-ttu-id="0dd5a-172">请转到 Windows 目录中，通常*C:\WINDOWS\assembly*。</span><span class="sxs-lookup"><span data-stu-id="0dd5a-172">Go to the Windows directory, typically *C:\WINDOWS\assembly*.</span></span>  

2. <span data-ttu-id="0dd5a-173">右键单击的 DLL 为其也希望将公钥，并选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="0dd5a-173">Right-click the DLL for which you want the public key, and then select **Properties**.</span></span> <span data-ttu-id="0dd5a-174">下表列出了为每个适配器和提供程序 Dll 的名称：</span><span class="sxs-lookup"><span data-stu-id="0dd5a-174">The following table lists the name of the DLLs for each adapter and provider:</span></span>  


   |                         <span data-ttu-id="0dd5a-175">适配器/.NET Framework 数据提供程序</span><span class="sxs-lookup"><span data-stu-id="0dd5a-175">Adapter/.NET Framework Data Provider</span></span>                         |       <span data-ttu-id="0dd5a-176">DLL 的名称</span><span class="sxs-lookup"><span data-stu-id="0dd5a-176">Name of the DLL</span></span>        |
   |--------------------------------------------------------------------------------------|------------------------------|
   |           [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]           |    <span data-ttu-id="0dd5a-177">Microsoft.Adapters.SAP</span><span class="sxs-lookup"><span data-stu-id="0dd5a-177">Microsoft.Adapters.SAP</span></span>    |
   |        [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]        |  <span data-ttu-id="0dd5a-178">Microsoft.Adapters.Siebel</span><span class="sxs-lookup"><span data-stu-id="0dd5a-178">Microsoft.Adapters.Siebel</span></span>   |
   |        [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]        | <span data-ttu-id="0dd5a-179">Microsoft.Adapters.OracleDB</span><span class="sxs-lookup"><span data-stu-id="0dd5a-179">Microsoft.Adapters.OracleDB</span></span>  |
   | [!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)] | <span data-ttu-id="0dd5a-180">Microsoft.Adapters.OracleEBS</span><span class="sxs-lookup"><span data-stu-id="0dd5a-180">Microsoft.Adapters.OracleEBS</span></span> |
   |            [!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]            |  <span data-ttu-id="0dd5a-181">Microsoft.Adapters.Sql.dll</span><span class="sxs-lookup"><span data-stu-id="0dd5a-181">Microsoft.Adapters.Sql.dll</span></span>  |
   |        [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]        |   <span data-ttu-id="0dd5a-182">Microsoft.Data.SAPClient</span><span class="sxs-lookup"><span data-stu-id="0dd5a-182">Microsoft.Data.SAPClient</span></span>   |
   |     [!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]     | <span data-ttu-id="0dd5a-183">Microsoft.Data.SiebelClient</span><span class="sxs-lookup"><span data-stu-id="0dd5a-183">Microsoft.Data.SiebelClient</span></span>  |


3. <span data-ttu-id="0dd5a-184">上**常规**选项卡上，**公钥标记**值是 DLL 的公共密钥。</span><span class="sxs-lookup"><span data-stu-id="0dd5a-184">On the **General** tab, the **Public Key Token** value is the public key for the DLL.</span></span> <span data-ttu-id="0dd5a-185">**版本**值是 DLL 的版本号。</span><span class="sxs-lookup"><span data-stu-id="0dd5a-185">The **Version** value is the version number for the DLL.</span></span>  

4. <span data-ttu-id="0dd5a-186">复制公钥，并选择**取消**。</span><span class="sxs-lookup"><span data-stu-id="0dd5a-186">Copy the public key, and then select **Cancel**.</span></span>  

## <a name="install-the-custom-rfcs"></a><span data-ttu-id="0dd5a-187">安装自定义 Rfc</span><span class="sxs-lookup"><span data-stu-id="0dd5a-187">Install the custom RFCs</span></span>  
<span data-ttu-id="0dd5a-188">只需*如果*你想要使用[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="0dd5a-188">Required only *if* you want to use the [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)].</span></span> <span data-ttu-id="0dd5a-189">请参阅[安装自定义 Rfc](../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)中[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]文档。</span><span class="sxs-lookup"><span data-stu-id="0dd5a-189">See [Install Custom RFCs](../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md) in the [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)] documentation.</span></span> 

> [!IMPORTANT]
>  <span data-ttu-id="0dd5a-190">如果使用早期版本的提供的自定义 Rfc [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]，则必须将其升级到此版本中提供的 Rfc。</span><span class="sxs-lookup"><span data-stu-id="0dd5a-190">If you are using an earlier version of the custom RFCs provided with the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)], then you must upgrade them to the RFCs provided with this release.</span></span> <span data-ttu-id="0dd5a-191">为此，删除早期的 Rfc，然后安装此版本中包含的 Rfc。</span><span class="sxs-lookup"><span data-stu-id="0dd5a-191">Do this by removing the earlier RFCs, and then installing the RFCs included with this release.</span></span>  

## <a name="install-the-enterprise-applications"></a><span data-ttu-id="0dd5a-192">安装企业应用程序</span><span class="sxs-lookup"><span data-stu-id="0dd5a-192">Install the enterprise applications</span></span>  
<span data-ttu-id="0dd5a-193">有关步骤和指南来安装不同企业 LOB 系统中，我们建议使用企业系统提供的安装指南。</span><span class="sxs-lookup"><span data-stu-id="0dd5a-193">For the steps and guidance to install the different enterprise LOB systems, we recommend you use the installation guides provided by the enterprise system.</span></span> <span data-ttu-id="0dd5a-194">如果有的话还引用特定的配置更改，其适配器文档。</span><span class="sxs-lookup"><span data-stu-id="0dd5a-194">Also refer to its adapter documentation for specific configuration changes, if any.</span></span>   

## <a name="installation-and-post-installation-checklist"></a><span data-ttu-id="0dd5a-195">安装和安装后清单</span><span class="sxs-lookup"><span data-stu-id="0dd5a-195">Installation and post-installation checklist</span></span>  

- <span data-ttu-id="0dd5a-196">请确保安装所有[必备软件](../adapters-and-accelerators/software-prerequisites-for-biztalk-adapter-pack-2016.md)使用正确的安装选项。</span><span class="sxs-lookup"><span data-stu-id="0dd5a-196">Make sure you installed all the [software prerequisites](../adapters-and-accelerators/software-prerequisites-for-biztalk-adapter-pack-2016.md) with the correct installation option.</span></span>

- <span data-ttu-id="0dd5a-197">请确保已安装在计算机上安装的企业 LOB 应用程序的受支持的版本[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="0dd5a-197">Make sure you have the supported version of the enterprise LOB applications installed on your computer where you installed the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="0dd5a-198">请参阅[受支持的业务线 (LOB) 系统](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-systems.aspx)。</span><span class="sxs-lookup"><span data-stu-id="0dd5a-198">See [Supported Line-of-Business (LOB) systems](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-systems.aspx).</span></span>  

- <span data-ttu-id="0dd5a-199">若要安装仅适用于企业你想要连接的 LOB 系统的适配器，请确保你安装[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]使用**自定义**安装选项。</span><span class="sxs-lookup"><span data-stu-id="0dd5a-199">To install only the adapter for the enterprise LOB system you want to connect, make sure you installed the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] using the **Custom** installation option.</span></span> <span data-ttu-id="0dd5a-200">请确保未使用**完成**安装选项。</span><span class="sxs-lookup"><span data-stu-id="0dd5a-200">Make sure you did not use the **Complete** installation option.</span></span> <span data-ttu-id="0dd5a-201">请参阅[安装的 BizTalk 适配器包](../adapters-and-accelerators/installing-the-biztalk-adapter-pack-2016.md)。</span><span class="sxs-lookup"><span data-stu-id="0dd5a-201">See [Installing the BizTalk Adapter Pack](../adapters-and-accelerators/installing-the-biztalk-adapter-pack-2016.md).</span></span>  

- <span data-ttu-id="0dd5a-202">如果你想要进行 SAP 系统使用 tRFC 调用[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]，请确保 SQL Server 数据库中创建所需的表。</span><span class="sxs-lookup"><span data-stu-id="0dd5a-202">If you want to make tRFC calls to the SAP system using the [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)], make sure you create the required tables in a SQL Server database.</span></span> <span data-ttu-id="0dd5a-203">请参阅**创建 SQL Server 数据库对象**（在本主题中）。</span><span class="sxs-lookup"><span data-stu-id="0dd5a-203">See **Create SQL Server Database objects** (in this topic).</span></span>

- <span data-ttu-id="0dd5a-204">运行时[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]安装向导中，可能会收到指示安装程序无法注册绑定的错误消息。</span><span class="sxs-lookup"><span data-stu-id="0dd5a-204">While running the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] setup wizard, you may get an error message that states the setup failed to register the bindings.</span></span> <span data-ttu-id="0dd5a-205">如果是这样，请手动注册它们。</span><span class="sxs-lookup"><span data-stu-id="0dd5a-205">If so, register them manually.</span></span> <span data-ttu-id="0dd5a-206">请参阅**注册适配器绑定**（在本主题中）。</span><span class="sxs-lookup"><span data-stu-id="0dd5a-206">See **Register the adapter bindings** (in this topic).</span></span>  

- <span data-ttu-id="0dd5a-207">如果您选择安装[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]作为的一部分[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]安装，请确保在 SAP 系统上安装自定义 Rfc。</span><span class="sxs-lookup"><span data-stu-id="0dd5a-207">If you chose to install the [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)] as part of the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] installation, make sure you install the custom RFCs on the SAP system.</span></span> <span data-ttu-id="0dd5a-208">请参阅[安装自定义 Rfc](../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)。</span><span class="sxs-lookup"><span data-stu-id="0dd5a-208">See [Install Custom RFCs](../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md).</span></span>

## <a name="more-good-info"></a><span data-ttu-id="0dd5a-209">更多有用信息</span><span class="sxs-lookup"><span data-stu-id="0dd5a-209">More good info</span></span>
[<span data-ttu-id="0dd5a-210">更改或删除 BizTalk 适配器包</span><span class="sxs-lookup"><span data-stu-id="0dd5a-210">Change or remove the BizTalk Adapter Pack</span></span>](../adapters-and-accelerators/update-or-uninstall-the-biztalk-adapter-pack-2016.md)  
[<span data-ttu-id="0dd5a-211">BizTalk 适配器包常见问题解答</span><span class="sxs-lookup"><span data-stu-id="0dd5a-211">BizTalk Adapter Pack FAQ</span></span>](../adapters-and-accelerators/frequently-asked-questions-for-the-biztalk-adapter-pack.md)