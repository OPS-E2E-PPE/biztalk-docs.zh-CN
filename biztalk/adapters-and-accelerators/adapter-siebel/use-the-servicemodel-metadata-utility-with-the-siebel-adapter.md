---
title: "使用 ServiceModel 元数据实用工具 BizTalk 适配器为 Siebel eBusiness Applications |Microsoft 文档"
description: "使用 svcutil.exe，对于非默认绑定，或使用 Siebel 适配器-BizTalk 适配器包 (BAP) 中创建的 WCF 客户端类或 WCF 服务协定"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 03d16481-cc8b-4e28-a33c-92e48a9a7e8f
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a0bcf80d4a1ea9fc6b54403faa14084816e413be
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="using-the-servicemodel-metadata-utility-tool-with-the-biztalk-adapter-for-siebel-ebusiness-applications"></a><span data-ttu-id="1f05a-103">使用 ServiceModel 元数据实用工具 BizTalk 适配器为 Siebel eBusiness Applications</span><span class="sxs-lookup"><span data-stu-id="1f05a-103">Using the ServiceModel Metadata Utility Tool with the BizTalk Adapter for Siebel eBusiness Applications</span></span>
<span data-ttu-id="1f05a-104">你可以使用 ServiceModel 元数据实用工具 (svcutil.exe) 生成操作的 WCF 客户端类，[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]公开。</span><span class="sxs-lookup"><span data-stu-id="1f05a-104">You can use the ServiceModel Metadata Utility Tool (svcutil.exe) to generate a WCF client class for operations that the [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] exposes.</span></span> <span data-ttu-id="1f05a-105">运行 svcutil.exe 以生成 WCF 客户端类后，你可以在你的代码中包含生成的文件和创建要在 Siebel 系统上执行操作的 WCF 客户端类的实例。</span><span class="sxs-lookup"><span data-stu-id="1f05a-105">After you run svcutil.exe to generate a WCF client class, you can include the generated file in your code and create instances of the WCF client class to perform operations on the Siebel system.</span></span>  
  
 <span data-ttu-id="1f05a-106">使用 svcutil.exe 需要你提供一个连接 URI，其中包含凭据。</span><span class="sxs-lookup"><span data-stu-id="1f05a-106">Using svcutil.exe requires you to supply a connection URI that contains credentials.</span></span> <span data-ttu-id="1f05a-107">因为，默认情况下，[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]禁用凭据在连接 URI，你必须配置要使用的非默认绑定的 svcutil.exe [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="1f05a-107">Because, by default, the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] disables credentials in the connection URI, you must configure svcutil.exe to use a non-default binding for the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span> <span data-ttu-id="1f05a-108">你还可以在非默认绑定中配置其他绑定属性。</span><span class="sxs-lookup"><span data-stu-id="1f05a-108">You can also configure other binding properties in the non-default binding.</span></span>  
  
 <span data-ttu-id="1f05a-109">以下部分说明如何配置 svcutil.exe 以及如何使用 svcutil.exe 生成 WCF 客户端代码[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="1f05a-109">The following sections show you how to configure svcutil.exe and how to use svcutil.exe to generate WCF client code with the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span>  
  
##  <a name="BKMK_ConfigureSvcutil"></a><span data-ttu-id="1f05a-110">配置非默认绑定的 svcutil.exe</span><span class="sxs-lookup"><span data-stu-id="1f05a-110">Configure svcutil.exe for a non-default binding</span></span>   
 <span data-ttu-id="1f05a-111">若要配置为使用非默认绑定的 svcutil.exe，你必须创建 svcutil.exe 的本地副本，然后创建或修改 svcutil.exe.config 配置文件的本地副本。</span><span class="sxs-lookup"><span data-stu-id="1f05a-111">To configure svcutil.exe to use a non-default binding, you must create a local copy of svcutil.exe and then create or modify a local copy of the svcutil.exe.config configuration file.</span></span>  
  
 
1.  <span data-ttu-id="1f05a-112">创建一个文件夹，并将 svcutil.exe 复制到新文件夹。</span><span class="sxs-lookup"><span data-stu-id="1f05a-112">Create a folder, and copy svcutil.exe into the new folder.</span></span> <span data-ttu-id="1f05a-113">你通常可以找到 svcutil.exe 在 Windows SDK 安装位置，具体而言，C:\Program Files\Microsoft SDKs\Windows\v6.0\Bin。</span><span class="sxs-lookup"><span data-stu-id="1f05a-113">You can typically find svcutil.exe at the Windows SDK installation location, specifically, C:\Program Files\Microsoft SDKs\Windows\v6.0\Bin.</span></span>  
  
2.  <span data-ttu-id="1f05a-114">创建名为的新文件夹中的 svcutil.exe.config 的文件。</span><span class="sxs-lookup"><span data-stu-id="1f05a-114">Create a file named svcutil.exe.config in the new folder.</span></span>  
  
3.  <span data-ttu-id="1f05a-115">将一个绑定和客户端终结点添加到 svcutil.exe.config 文件中。</span><span class="sxs-lookup"><span data-stu-id="1f05a-115">Add a binding and a client endpoint to the svcutil.exe.config file.</span></span> <span data-ttu-id="1f05a-116">你必须从新的文件夹，以确保使用正确的配置运行 svcutil.exe。</span><span class="sxs-lookup"><span data-stu-id="1f05a-116">You must run svcutil.exe from the new folder to ensure that the correct configuration is used.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="1f05a-117">客户端终结点的名称属性必须指定连接 URI 中所使用的方案。</span><span class="sxs-lookup"><span data-stu-id="1f05a-117">The name attribute of the client endpoint must specify the scheme used in the connection URI.</span></span> <span data-ttu-id="1f05a-118">此值区分大小写。</span><span class="sxs-lookup"><span data-stu-id="1f05a-118">This value is case-sensitive.</span></span>  
  
    ```  
    <configuration>  
      <system.serviceModel>  
        <client>  
          <!-- the name should match the required scheme of the Metadata Exchange endpoint   
          and the contract should be "IMetadataExchange" -->  
          <endpoint name="siebel"  
            binding="siebelBinding"  
            bindingConfiguration="SiebelBinding"  
            contract="IMetadataExchange" />  
        </client>  
        <bindings>  
          <siebelBinding>  
            <binding name="SiebelBinding" acceptCredentialsInUri="true" />  
          </siebelBinding>  
        </bindings>  
  
      </system.serviceModel>  
  
    </configuration>  
  
    ```  
  
> [!NOTE]
>  <span data-ttu-id="1f05a-119">你可以设置的绑定属性的任何[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]在绑定配置。</span><span class="sxs-lookup"><span data-stu-id="1f05a-119">You can set any of the binding properties of the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] in the binding configuration.</span></span>  
  
 <span data-ttu-id="1f05a-120">有关配置 svcutil.exe 的非默认绑定的详细信息，请参阅 WCF 文档中的"自定义安全元数据终结点"主题[http://go.microsoft.com/fwlink/?LinkId=96077](http://go.microsoft.com/fwlink/?LinkId=96077)。</span><span class="sxs-lookup"><span data-stu-id="1f05a-120">For more information about configuring a non-default binding for svcutil.exe, see the "Custom Secure Metadata Endpoint" topic in the WCF documentation at [http://go.microsoft.com/fwlink/?LinkId=96077](http://go.microsoft.com/fwlink/?LinkId=96077).</span></span>  
  
## <a name="creating-a-wcf-client-class-with-svcutilexe"></a><span data-ttu-id="1f05a-121">使用 svcutil.exe 创建 WCF 客户端类</span><span class="sxs-lookup"><span data-stu-id="1f05a-121">Creating a WCF Client Class with svcutil.exe</span></span>  
 <span data-ttu-id="1f05a-122">若要使用 svcutil.exe 生成的 WCF 客户端代码[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]，你必须提供连接 URI，指定**IMetadataExchange** (mex) 终结点的操作或操作所需 svcutil.exe 生成代码。</span><span class="sxs-lookup"><span data-stu-id="1f05a-122">To use svcutil.exe to generate WCF client code for the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], you must supply a connection URI that specifies an **IMetadataExchange** (mex) endpoint and the operation or operations for which you want svcutil.exe to generate code.</span></span> <span data-ttu-id="1f05a-123">你还必须在连接 URI 中指定 Siebel 系统的连接凭据。</span><span class="sxs-lookup"><span data-stu-id="1f05a-123">You must also specify connection credentials for the Siebel system in the connection URI.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1f05a-124">你可以使用 svcutil.exe 与之前[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]，你必须将其配置为使用非默认绑定; 有关如何执行此操作，请参阅[为 Siebel 适配器配置 svcutil.exe](#BKMK_ConfigureSvcutil)。</span><span class="sxs-lookup"><span data-stu-id="1f05a-124">Before you can use svcutil.exe with the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], you must configure it to use a non-default binding; for information about how to do this, see [Configuring svcutil.exe for the Siebel Adapter](#BKMK_ConfigureSvcutil).</span></span>  
  
 <span data-ttu-id="1f05a-125">指定在 mex 终结点和目标操作[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]连接 URI 按以下方式：</span><span class="sxs-lookup"><span data-stu-id="1f05a-125">You specify a mex endpoint and target operations in the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] connection URI in the following manner:</span></span>  
  
-   <span data-ttu-id="1f05a-126">你必须在 query_string 中包含"wsdl"参数。</span><span class="sxs-lookup"><span data-stu-id="1f05a-126">You must include the "wsdl" parameter in the query_string.</span></span> <span data-ttu-id="1f05a-127">如果它是 query_string 中的第一个参数，其指定为问号 （？） 之后。</span><span class="sxs-lookup"><span data-stu-id="1f05a-127">If it is the first parameter in the query_string, it is specified just after the question mark (?).</span></span> <span data-ttu-id="1f05a-128">如果它不是第一个参数，它应在它前面加一个与号 (&)。</span><span class="sxs-lookup"><span data-stu-id="1f05a-128">If it is not the first parameter, it should be preceded with an ampersand (&).</span></span>  
  
-   <span data-ttu-id="1f05a-129">你必须执行一个或多个"op"参数"wsdl"的参数。</span><span class="sxs-lookup"><span data-stu-id="1f05a-129">You must follow the "wsdl" parameter by one or more "op" parameters.</span></span> <span data-ttu-id="1f05a-130">每个"op"参数前面是一个与号 (&)，并指定目标操作的节点 ID。</span><span class="sxs-lookup"><span data-stu-id="1f05a-130">Each "op" parameter is preceded by an ampersand (&) and specifies the node ID of a target operation.</span></span>  
  
 <span data-ttu-id="1f05a-131">下面的两个示例演示如何通过使用 svcutil.exe 来面向各种操作。</span><span class="sxs-lookup"><span data-stu-id="1f05a-131">The following two examples show how to target various operations by using svcutil.exe.</span></span>  
  
 <span data-ttu-id="1f05a-132">此示例创建插入操作在 ACCOUNT\ACCOUNT 业务对象上的 WCF 客户端类。</span><span class="sxs-lookup"><span data-stu-id="1f05a-132">This example creates a WCF client class for an insert operation on the ACCOUNT\ACCOUNT Business Object.</span></span>  
  
 <span data-ttu-id="1f05a-133">**。 \svcutil"siebel://Username=YourUserName;密码 =YourPassword@Siebel_server:1234？SiebelEnterpriseServer = ent_server SiebelObjectManager = obj_mgr 和语言 = enu （wsdl） 操作 = http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert"**</span><span class="sxs-lookup"><span data-stu-id="1f05a-133">**.\svcutil "siebel://Username=YourUserName;Password=YourPassword@Siebel_server:1234?SiebelEnterpriseServer=ent_server&SiebelObjectManager=obj_mgr&Language=enu&wsdl&op=http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert"**</span></span>  
  
 <span data-ttu-id="1f05a-134">此示例创建插入操作和删除操作在 ACCOUNT\ACCOUNT 业务对象上的 WCF 客户端类。</span><span class="sxs-lookup"><span data-stu-id="1f05a-134">This example creates a WCF client class for both an insert operation and a delete operation on the ACCOUNT\ACCOUNT Business Object.</span></span>  
  
 <span data-ttu-id="1f05a-135">**。 \svcutil"siebel://Username=YourUserName;密码 =YourPassword@Siebel_server:1234？SiebelEnterpriseServer = ent_server SiebelObjectManager = obj_mgr 和语言 = enu （wsdl） 操作 = http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert 操作 = http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Delete"**</span><span class="sxs-lookup"><span data-stu-id="1f05a-135">**.\svcutil " siebel://Username=YourUserName;Password=YourPassword@Siebel_server:1234?SiebelEnterpriseServer=ent_server&SiebelObjectManager=obj_mgr&Language=enu&wsdl&op=http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert&op=http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Delete"**</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="1f05a-136">必须用引号引起来，在命令行上放置连接 URI。</span><span class="sxs-lookup"><span data-stu-id="1f05a-136">You must place the connection URI in quotation marks on the command line.</span></span> <span data-ttu-id="1f05a-137">否则，svcutil.exe 会尝试检索操作的元数据，[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]不支持。</span><span class="sxs-lookup"><span data-stu-id="1f05a-137">Otherwise, svcutil.exe attempts to retrieve metadata for operations that the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] does not support.</span></span> <span data-ttu-id="1f05a-138">这类尝试的结果不确定。</span><span class="sxs-lookup"><span data-stu-id="1f05a-138">The results of such an attempt are undefined.</span></span>  
  
 <span data-ttu-id="1f05a-139">默认情况下，svcutil.exe 将生成的代码文件中的 output.cs;但是，你可以更改输出文件的名称和许多其他选项，svcutil.exe 使用通过设置命令行开关。</span><span class="sxs-lookup"><span data-stu-id="1f05a-139">By default, svcutil.exe places the generated code in the output.cs file; however, you can change the name of the output file and many other options that svcutil.exe uses by setting command-line switches.</span></span>  
  
 <span data-ttu-id="1f05a-140">Svcutil.exe 不提供的功能 （例如，通过使用通配符） 搜索操作。</span><span class="sxs-lookup"><span data-stu-id="1f05a-140">Svcutil.exe does not provide the capability to search for operations (for example, by using wildcard characters).</span></span> <span data-ttu-id="1f05a-141">你必须显式指定要设定为目标的特定操作的节点 Id。</span><span class="sxs-lookup"><span data-stu-id="1f05a-141">You must explicitly specify node IDs for the specific operations you want to target.</span></span> <span data-ttu-id="1f05a-142">不能指定节点仅引用中的类别的 Id。</span><span class="sxs-lookup"><span data-stu-id="1f05a-142">You cannot specify node IDs that refer only to categories.</span></span> <span data-ttu-id="1f05a-143">有关节点 Id 的详细信息，[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]图面，请参阅[元数据的节点 Id](../../adapters-and-accelerators/adapter-siebel/metadata-node-ids1.md)。</span><span class="sxs-lookup"><span data-stu-id="1f05a-143">For more information about the node IDs that the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] surfaces, see [Metadata Node IDs](../../adapters-and-accelerators/adapter-siebel/metadata-node-ids1.md).</span></span>  
  
 <span data-ttu-id="1f05a-144">[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]提供了高级的浏览和搜索功能可以极大地简化生成 WCF 客户端类。</span><span class="sxs-lookup"><span data-stu-id="1f05a-144">The [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] provides advanced browse and search capabilities that can greatly simplify generating a WCF client class.</span></span> <span data-ttu-id="1f05a-145">有关详细信息[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，请参阅[生成 WCF 客户端或 Siebel 解决方案项目关联的 WCF 服务协定](../../adapters-and-accelerators/adapter-siebel/generate-a-wcf-client-or-a-wcf-service-contract-for-siebel-solution-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="1f05a-145">For more information about the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], see [Generate a WCF client or a WCF service contract for Siebel solution artifacts](../../adapters-and-accelerators/adapter-siebel/generate-a-wcf-client-or-a-wcf-service-contract-for-siebel-solution-artifacts.md).</span></span>  
  
