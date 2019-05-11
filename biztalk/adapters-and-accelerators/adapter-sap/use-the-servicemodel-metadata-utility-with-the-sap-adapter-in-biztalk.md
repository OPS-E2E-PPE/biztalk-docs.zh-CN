---
title: 用于 mySAP Business Suite 的 BizTalk 适配器使用 ServiceModel Metadata Utility Tool |Microsoft Docs
description: 使用 svcutil.exe 为非默认绑定，或若要使用 SAP 适配器的 BizTalk 适配器包 (BAP) 中创建 WCF 客户端类或 WCF 服务协定
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ServiceModel Metadata Utility Tool, creating a WCF Client Class or a WCF service contract with the tool
- ServiceModel Metadata Utility Tool, configuring the tool for the adapter
ms.assetid: 7ac08012-bb12-4983-9402-be84fe3997d8
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 12a7317ca742c6ce1909890a98738e36852f445d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372035"
---
# <a name="using-the-servicemodel-metadata-utility-tool-with-the-biztalk-adapter-for-mysap-business-suite"></a><span data-ttu-id="fd4f5-103">用于 mySAP Business Suite 的 BizTalk 适配器使用 ServiceModel Metadata Utility Tool</span><span class="sxs-lookup"><span data-stu-id="fd4f5-103">Using the ServiceModel Metadata Utility Tool with the BizTalk Adapter for mySAP Business Suite</span></span>
<span data-ttu-id="fd4f5-104">可以使用 ServiceModel Metadata Utility Tool (svcutil.exe) 生成 WCF 客户端类或操作的 WCF 服务协定 （接口） 的[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]公开。</span><span class="sxs-lookup"><span data-stu-id="fd4f5-104">You can use the ServiceModel Metadata Utility Tool (svcutil.exe) to generate a WCF client class or a WCF service contract (interface) for operations that the [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] exposes.</span></span> <span data-ttu-id="fd4f5-105">运行 svcutil.exe 来生成 WCF 客户端类或 WCF 服务协定后，您可以在代码中包含生成的文件和创建生成的类的实例或实现中生成的接口对 SAP 执行操作的 WCF 服务系统。</span><span class="sxs-lookup"><span data-stu-id="fd4f5-105">After you run svcutil.exe to generate either a WCF client class or a WCF service contract, you can include the generated file in your code and create instances of the generated class or implement a WCF service from the generated interface to perform operations on the SAP system.</span></span>  
  
 <span data-ttu-id="fd4f5-106">使用 svcutil.exe 要求您提供一个连接 URI，其中包含凭据。</span><span class="sxs-lookup"><span data-stu-id="fd4f5-106">Using svcutil.exe requires you to supply a connection URI that contains credentials.</span></span> <span data-ttu-id="fd4f5-107">因为，默认情况下[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]禁用凭据中的连接 URI，必须配置要使用的非默认绑定的 svcutil.exe [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="fd4f5-107">Because, by default, the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] disables credentials in the connection URI, you must configure svcutil.exe to use a non-default binding for the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="fd4f5-108">此外可以在非默认绑定; 中配置其他绑定属性例如，若要创建 BAPI 操作的 WCF 客户端，必须设置**EnableSafeTyping**属性绑定到**true**。</span><span class="sxs-lookup"><span data-stu-id="fd4f5-108">You can also configure other binding properties in the non-default binding; for example, to create a WCF client for BAPI operations, you must set the **EnableSafeTyping** binding property to **true**.</span></span>  
  
 <span data-ttu-id="fd4f5-109">以下部分介绍如何配置 svcutil.exe 以及如何使用 svcutil.exe 来生成 WCF 客户端代码或具有的 WCF 服务协定[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="fd4f5-109">The following sections show you how to configure svcutil.exe and how to use svcutil.exe to generate WCF client code or a WCF service contract with the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
##  <a name="BKMK_ConfigureSvcutil"></a> <span data-ttu-id="fd4f5-110">SAP 适配器的配置 svcutil.exe</span><span class="sxs-lookup"><span data-stu-id="fd4f5-110">Configuring svcutil.exe for the SAP Adapter</span></span>  
 <span data-ttu-id="fd4f5-111">若要配置 svcutil.exe 使用非默认绑定，您必须创建 svcutil.exe 的本地副本，然后创建或修改 svcutil.exe.config 配置文件的本地副本。</span><span class="sxs-lookup"><span data-stu-id="fd4f5-111">To configure svcutil.exe to use a non-default binding, you must create a local copy of svcutil.exe and then create or modify a local copy of the svcutil.exe.config configuration file.</span></span>  
  
1. <span data-ttu-id="fd4f5-112">创建一个文件夹，并将 svcutil.exe 复制到新文件夹。</span><span class="sxs-lookup"><span data-stu-id="fd4f5-112">Create a folder, and copy svcutil.exe into the new folder.</span></span> <span data-ttu-id="fd4f5-113">通常可以找到 svcutil.exe 在 Windows SDK 安装位置，具体而言，C:\Program Files\Microsoft SDKs\Windows\v6.0\Bin。</span><span class="sxs-lookup"><span data-stu-id="fd4f5-113">You can typically find svcutil.exe at the Windows SDK installation location, specifically, C:\Program Files\Microsoft SDKs\Windows\v6.0\Bin.</span></span>  
  
2. <span data-ttu-id="fd4f5-114">创建名为的新文件夹中的 svcutil.exe.config 的文件。</span><span class="sxs-lookup"><span data-stu-id="fd4f5-114">Create a file named svcutil.exe.config in the new folder.</span></span>  
  
3. <span data-ttu-id="fd4f5-115">将一个绑定和客户端终结点添加到 svcutil.exe.config 文件。</span><span class="sxs-lookup"><span data-stu-id="fd4f5-115">Add a binding and a client endpoint to the svcutil.exe.config file.</span></span> <span data-ttu-id="fd4f5-116">您必须从新的文件夹，以确保使用正确的配置运行 svcutil.exe。</span><span class="sxs-lookup"><span data-stu-id="fd4f5-116">You must run svcutil.exe from the new folder to ensure that the correct configuration is used.</span></span>  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="fd4f5-117">客户端终结点的 name 属性必须指定连接 URI 中使用的方案。</span><span class="sxs-lookup"><span data-stu-id="fd4f5-117">The name attribute of the client endpoint must specify the scheme used in the connection URI.</span></span> <span data-ttu-id="fd4f5-118">此值区分大小写。</span><span class="sxs-lookup"><span data-stu-id="fd4f5-118">This value is case-sensitive.</span></span>  
  
   ```  
   <configuration>  
     <system.serviceModel>  
       <client>  
         <!-- the name should match the required scheme of the WS-Metadata Exchange endpoint   
         and the contract should be "IMetadataExchange" -->  
         <endpoint name="sap"  
                   binding="sapBinding"  
                   bindingConfiguration="SAPBinding"  
                   contract="IMetadataExchange" />  
       </client>  
       <bindings>  
         <sapBinding>  
           <binding name="SAPBinding" acceptCredentialsInUri="true"/>  
         </sapBinding>  
       </bindings>  
  
     </system.serviceModel>  
  
   </configuration>  
   ```  
  
   <span data-ttu-id="fd4f5-119">您可以设置的绑定属性的任何[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]绑定配置中。</span><span class="sxs-lookup"><span data-stu-id="fd4f5-119">You can set any of the binding properties of the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] in the binding configuration.</span></span> <span data-ttu-id="fd4f5-120">例如，可以指定要使用 svcutil.exe 生成 BAPI 操作的 WCF 客户端的以下非默认绑定。</span><span class="sxs-lookup"><span data-stu-id="fd4f5-120">For example, you could specify the following non-default binding to use svcutil.exe to generate a WCF client for BAPI operations.</span></span>  
  
```  
<bindings>  
  <sapBinding>  
    <binding name="SAPBinding" acceptCredentialsInUri="true"/>  
  </sapBinding>  
</bindings>  
```  
  
 <span data-ttu-id="fd4f5-121">有关配置 svcutil.exe 的非默认绑定的详细信息，请参阅[自定义安全元数据终结点](https://msdn.microsoft.com/library/aa395212.aspx)。</span><span class="sxs-lookup"><span data-stu-id="fd4f5-121">For more information about configuring a non-default binding for svcutil.exe, see the [Custom Secure Metadata Endpoint](https://msdn.microsoft.com/library/aa395212.aspx).</span></span>
  
## <a name="creating-a-wcf-client-class-or-a-wcf-service-contract-with-svcutilexe"></a><span data-ttu-id="fd4f5-122">使用 svcutil.exe 创建 WCF 客户端类或 WCF 服务约定</span><span class="sxs-lookup"><span data-stu-id="fd4f5-122">Creating a WCF Client Class or a WCF Service Contract with svcutil.exe</span></span>  
 <span data-ttu-id="fd4f5-123">若要使用 svcutil.exe 为生成 WCF 客户端代码或 WCF 服务协定 （接口） [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，必须提供 URI，指定的 WS-元数据交换 (MEX) 终结点的操作或操作要到 svcutil.exe 的连接生成代码。</span><span class="sxs-lookup"><span data-stu-id="fd4f5-123">To use svcutil.exe to generate WCF client code or a WCF service contract (interface) for the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], you must supply a connection URI that specifies a WS-Metadata Exchange (MEX) endpoint and the operation or operations for which you want svcutil.exe to generate code.</span></span> <span data-ttu-id="fd4f5-124">此外必须在连接 URI 中指定为 SAP 系统的连接凭据。</span><span class="sxs-lookup"><span data-stu-id="fd4f5-124">You must also specify connection credentials for the SAP system in the connection URI.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fd4f5-125">您可以使用 svcutil.exe 与之前[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，你必须将其配置为使用非默认绑定; 了解有关如何执行此操作，请参阅[SAP 适配器的配置 svcutil.exe](#BKMK_ConfigureSvcutil)。</span><span class="sxs-lookup"><span data-stu-id="fd4f5-125">Before you can use svcutil.exe with the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], you must configure it to use a non-default binding; for information about how to do this, see [Configuring svcutil.exe for the SAP Adapter](#BKMK_ConfigureSvcutil).</span></span>  
  
 <span data-ttu-id="fd4f5-126">指定在 MEX 终结点和目标操作[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]连接 URI 按以下方式：</span><span class="sxs-lookup"><span data-stu-id="fd4f5-126">You specify a MEX endpoint and target operations in the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] connection URI in the following manner:</span></span>  
  
- <span data-ttu-id="fd4f5-127">您必须在查询字符串中包含"wsdl"参数。</span><span class="sxs-lookup"><span data-stu-id="fd4f5-127">You must include the "wsdl" parameter in the query string.</span></span> <span data-ttu-id="fd4f5-128">如果它是查询字符串中的第一个参数，则将其指定之后问号 （？）。</span><span class="sxs-lookup"><span data-stu-id="fd4f5-128">If it is the first parameter in the query string, it is specified just after the question mark (?).</span></span> <span data-ttu-id="fd4f5-129">如果它不是第一个参数，它应在前面加上 & 号 (&)。</span><span class="sxs-lookup"><span data-stu-id="fd4f5-129">If it is not the first parameter, it should be preceded with an ampersand (&).</span></span>  
  
- <span data-ttu-id="fd4f5-130">必须遵循一个或多个"op"参数"wsdl"的参数。</span><span class="sxs-lookup"><span data-stu-id="fd4f5-130">You must follow the "wsdl" parameter by one or more "op" parameters.</span></span> <span data-ttu-id="fd4f5-131">每个"op"参数的前面有与号 (&)，并指定目标操作的节点 ID。</span><span class="sxs-lookup"><span data-stu-id="fd4f5-131">Each "op" parameter is preceded by an ampersand (&) and specifies the node ID of a target operation.</span></span>  
  
  <span data-ttu-id="fd4f5-132">以下三个示例演示如何通过使用 svcutil.exe 来面向各种操作。</span><span class="sxs-lookup"><span data-stu-id="fd4f5-132">The following three examples show how to target various operations by using svcutil.exe.</span></span>  
  
  <span data-ttu-id="fd4f5-133">此示例中为 RFC_CALCULATE_TAXES 创建 WCF 客户端类。</span><span class="sxs-lookup"><span data-stu-id="fd4f5-133">This example creates a WCF client class for RFC_CALCULATE_TAXES.</span></span>  
  
  <span data-ttu-id="fd4f5-134">**.\svcutil "sap://User=YourUserName;Passwd=YourPassword;Client=800;Lang=EN;@a/YourSAPHost/00?wsdl&op=http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CALCULATE_TAXES"**</span><span class="sxs-lookup"><span data-stu-id="fd4f5-134">**.\svcutil "sap://User=YourUserName;Passwd=YourPassword;Client=800;Lang=EN;@a/YourSAPHost/00?wsdl&op=http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CALCULATE_TAXES"**</span></span>  
  
  <span data-ttu-id="fd4f5-135">此示例中为 SALESORDER_CREATEFROMDAT201 和 SALESORDER_CREATEFROMDAT202 IDOC 创建 WCF 客户端类。</span><span class="sxs-lookup"><span data-stu-id="fd4f5-135">This example creates a WCF client class for both the SALESORDER_CREATEFROMDAT201 and SALESORDER_CREATEFROMDAT202 IDOC.</span></span>  
  
  <span data-ttu-id="fd4f5-136">**.\svcutil "sap://User=YourUserName;Passwd=YourPassword;Client=800;Lang=EN;@a/YourSAPHost/00?wsdl&op=http://Microsoft.LobServices.Sap/2007/03/Idoc/3/SALESORDER_CREATEFROMDAT201//620/Send&op=http://Microsoft.LobServices.Sap/2007/03/Idoc/3/SALESORDER_CREATEFROMDAT202//620/Send"**</span><span class="sxs-lookup"><span data-stu-id="fd4f5-136">**.\svcutil "sap://User=YourUserName;Passwd=YourPassword;Client=800;Lang=EN;@a/YourSAPHost/00?wsdl&op=http://Microsoft.LobServices.Sap/2007/03/Idoc/3/SALESORDER_CREATEFROMDAT201//620/Send&op=http://Microsoft.LobServices.Sap/2007/03/Idoc/3/SALESORDER_CREATEFROMDAT202//620/Send"**</span></span>  
  
  <span data-ttu-id="fd4f5-137">此示例创建 WCF 服务协定以接收来自 SAP 系统的 SALESORDER_CREATEFROMDAT201 IDOC。</span><span class="sxs-lookup"><span data-stu-id="fd4f5-137">This example creates a WCF service contract to receive the SALESORDER_CREATEFROMDAT201 IDOC from the SAP system.</span></span> <span data-ttu-id="fd4f5-138">节点 ID 指定接收操作。</span><span class="sxs-lookup"><span data-stu-id="fd4f5-138">The NODE ID specifies a Receive operation.</span></span> <span data-ttu-id="fd4f5-139">此示例中处理检索元数据，因为没有需要的连接 URI query_string 中指定的侦听参数。</span><span class="sxs-lookup"><span data-stu-id="fd4f5-139">Because this example deals with retrieving metadata, there is no need to specify the listener parameters in the query_string of the connection URI.</span></span>  
  
  <span data-ttu-id="fd4f5-140">**.\svcutil "sap://User=YourUserName;Passwd=YourPassword;Client=800;Lang=EN;@a/YourSAPHost/00?wsdl&op=http://Microsoft.LobServices.Sap/2007/03/Idoc/3/SALESORDER_CREATEFROMDAT201//620/Receive"**</span><span class="sxs-lookup"><span data-stu-id="fd4f5-140">**.\svcutil "sap://User=YourUserName;Passwd=YourPassword;Client=800;Lang=EN;@a/YourSAPHost/00?wsdl&op=http://Microsoft.LobServices.Sap/2007/03/Idoc/3/SALESORDER_CREATEFROMDAT201//620/Receive"**</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="fd4f5-141">必须将连接 URI 放在命令行上的引号。</span><span class="sxs-lookup"><span data-stu-id="fd4f5-141">You must place the connection URI in quotation marks on the command line.</span></span> <span data-ttu-id="fd4f5-142">否则，svcutil.exe 会尝试检索操作的元数据的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]不支持。</span><span class="sxs-lookup"><span data-stu-id="fd4f5-142">Otherwise, svcutil.exe attempts to retrieve metadata for operations that the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] does not support.</span></span> <span data-ttu-id="fd4f5-143">这类尝试的结果不确定。</span><span class="sxs-lookup"><span data-stu-id="fd4f5-143">The results of such an attempt are undefined.</span></span>  
  
 <span data-ttu-id="fd4f5-144">默认情况下，svcutil.exe 将生成的代码 output.cs 文件;但是，可以更改输出文件的名称和许多其他选项，svcutil.exe 使用通过设置命令行开关。</span><span class="sxs-lookup"><span data-stu-id="fd4f5-144">By default, svcutil.exe places the generated code in the output.cs file; however, you can change the name of the output file and many other options that svcutil.exe uses by setting command-line switches.</span></span> <span data-ttu-id="fd4f5-145">该 svcutil.exe 支持的选项的详细信息，请参阅[ServiceModel Metadata Utility Tool (Svcutil.exe)](https://msdn.microsoft.com/library/aa347733.aspx)。</span><span class="sxs-lookup"><span data-stu-id="fd4f5-145">For more information about the options that svcutil.exe supports, see the [ServiceModel Metadata Utility Tool (Svcutil.exe)](https://msdn.microsoft.com/library/aa347733.aspx).</span></span>
  
 <span data-ttu-id="fd4f5-146">Svcutil.exe 不提供搜索操作 （例如，通过使用通配符） 的功能。</span><span class="sxs-lookup"><span data-stu-id="fd4f5-146">Svcutil.exe does not provide the capability to search for operations (for example, by using wildcard characters).</span></span> <span data-ttu-id="fd4f5-147">必须显式指定你想要针对的特定操作的节点 Id。</span><span class="sxs-lookup"><span data-stu-id="fd4f5-147">You must explicitly specify node IDs for the specific operations you want to target.</span></span> <span data-ttu-id="fd4f5-148">操作的节点 ID 等于其消息的操作字符串。</span><span class="sxs-lookup"><span data-stu-id="fd4f5-148">The node ID of an operation is equivalent to its message action string.</span></span> <span data-ttu-id="fd4f5-149">不能指定节点只能引用类别的 Id。</span><span class="sxs-lookup"><span data-stu-id="fd4f5-149">You cannot specify node IDs that refer only to categories.</span></span> <span data-ttu-id="fd4f5-150">详细了解节点 Id 的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]图面，请参阅[元数据节点 Id](../../adapters-and-accelerators/adapter-sap/metadata-node-ids4.md)。</span><span class="sxs-lookup"><span data-stu-id="fd4f5-150">For more information about the node IDs that the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] surfaces, see [Metadata Node IDs](../../adapters-and-accelerators/adapter-sap/metadata-node-ids4.md).</span></span>  
  
 <span data-ttu-id="fd4f5-151">[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]提供高级的浏览和搜索功能，可以极大地简化生成 WCF 客户端类和 WCF 服务约定。</span><span class="sxs-lookup"><span data-stu-id="fd4f5-151">The [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] provides advanced browse and search capabilities that can greatly simplify generating a WCF client class and WCF service contract.</span></span> <span data-ttu-id="fd4f5-152">有关详细信息[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，请参阅[生成 WCF 客户端或 SAP 解决方案项目的 WCF 服务约定](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="fd4f5-152">For more information about the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], see [Generate a WCF client or a WCF service contract for SAP solution artifacts](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md).</span></span>  
  
