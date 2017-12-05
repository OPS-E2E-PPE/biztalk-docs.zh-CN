---
title: "有关数据提供程序类型读取 SAP 连接字符串 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Data Provider for SAP, connection string
- ADO, connection string
ms.assetid: 7a46eaae-604f-4bae-924b-9f6d43a6e8a0
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e77219fb74b7af377953a3761c4d9f241b3a8bd0
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="read-about-data-provider-types-for-the-sap-connection-string"></a><span data-ttu-id="05b58-102">有关数据提供程序类型读取 SAP 连接字符串</span><span class="sxs-lookup"><span data-stu-id="05b58-102">Read about Data Provider types for the SAP Connection String</span></span>
<span data-ttu-id="05b58-103">若要建立到 SAP 系统的连接，ADO.NET 客户端必须在连接字符串的形式指定 SAP 连接属性。</span><span class="sxs-lookup"><span data-stu-id="05b58-103">To establish connectivity to an SAP system, ADO.NET clients must specify the SAP connection properties in the form of a connection string.</span></span> <span data-ttu-id="05b58-104">SAP ADO 连接字符串的格式如下所示：</span><span class="sxs-lookup"><span data-stu-id="05b58-104">The format for the SAP ADO connection string looks like:</span></span>  
  
```  
[Property1]=[Value1];[Property2]=[Value2];....  
```  
  
 <span data-ttu-id="05b58-105">要连接到 SAP 系统使用的连接字符串[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]可以具有以下类型：</span><span class="sxs-lookup"><span data-stu-id="05b58-105">The connection string to connect to an SAP system using the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] can have the following types:</span></span>  
  
-   <span data-ttu-id="05b58-106">**答： 类型**在其中连接 URI 指定通过该应用程序服务器的应用程序基于主机的连接[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]连接到 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="05b58-106">**TYPE A:** An application host–based connection in which the connection URI specifies an application server through which the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] connects to the SAP system.</span></span>  
  
-   <span data-ttu-id="05b58-107">**类型 b:**连接 URI 在其中指定了消息和服务器之间的负载平衡的连接[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]连接到 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="05b58-107">**TYPE B:** A load-balanced connection in which the connection URI specifies a message server through which the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] connects to the SAP system.</span></span>  
  
-   <span data-ttu-id="05b58-108">**类型 d:**在其中连接 URI 指定包含 SAP 系统的连接参数的 saprfc.ini 文件中的目标的基于目标的连接。</span><span class="sxs-lookup"><span data-stu-id="05b58-108">**TYPE D:** A destination-based connection in which the connection URI specifies a destination in the saprfc.ini file that contains the connection parameters for the SAP system.</span></span>  
  
 <span data-ttu-id="05b58-109">下表介绍如何在连接 URI 中指定这些连接。</span><span class="sxs-lookup"><span data-stu-id="05b58-109">The following table describes how these connections are specified in the connection URI.</span></span>  
  
|<span data-ttu-id="05b58-110">TYPE</span><span class="sxs-lookup"><span data-stu-id="05b58-110">TYPE</span></span>|<span data-ttu-id="05b58-111">属性 1</span><span class="sxs-lookup"><span data-stu-id="05b58-111">Property 1</span></span>|<span data-ttu-id="05b58-112">属性 2</span><span class="sxs-lookup"><span data-stu-id="05b58-112">Property 2</span></span>|<span data-ttu-id="05b58-113">Description</span><span class="sxs-lookup"><span data-stu-id="05b58-113">Description</span></span>|  
|----------|----------------|----------------|-----------------|  
|<span data-ttu-id="05b58-114">仅当辅助副本配置为使用手动故障转移模式，并且至少一个辅助副本当前与主要副本同步时，</span><span class="sxs-lookup"><span data-stu-id="05b58-114">A</span></span>|<span data-ttu-id="05b58-115">ASHOST （应用程序服务器主机）</span><span class="sxs-lookup"><span data-stu-id="05b58-115">ASHOST (Application Server Host)</span></span>|<span data-ttu-id="05b58-116">SYSNR （SAP 系统编号）</span><span class="sxs-lookup"><span data-stu-id="05b58-116">SYSNR (SAP System Number)</span></span>|<span data-ttu-id="05b58-117">指定的应用程序基于主机的连接。</span><span class="sxs-lookup"><span data-stu-id="05b58-117">Specifies an application host-based connection.</span></span>|  
|<span data-ttu-id="05b58-118">B</span><span class="sxs-lookup"><span data-stu-id="05b58-118">B</span></span>|<span data-ttu-id="05b58-119">MSHOST （消息服务器主机）</span><span class="sxs-lookup"><span data-stu-id="05b58-119">MSHOST (Message Server Host)</span></span>|<span data-ttu-id="05b58-120">R3NAME （SAP R3 名称）</span><span class="sxs-lookup"><span data-stu-id="05b58-120">R3NAME (SAP R3 Name)</span></span>|<span data-ttu-id="05b58-121">指定负载平衡通过消息服务器的连接。</span><span class="sxs-lookup"><span data-stu-id="05b58-121">Specifies a load balancing connection through a message server.</span></span> <span data-ttu-id="05b58-122">对于负载平衡连接，可以指定可选的服务器组的步骤。</span><span class="sxs-lookup"><span data-stu-id="05b58-122">For a load balancing connection, an optional server group can be specified.</span></span>|  
|<span data-ttu-id="05b58-123">D</span><span class="sxs-lookup"><span data-stu-id="05b58-123">D</span></span>|<span data-ttu-id="05b58-124">目标 （包含 saprfc.ini 文件中的连接参数的目标）</span><span class="sxs-lookup"><span data-stu-id="05b58-124">DEST (Destination that contains the connection parameters in the saprfc.ini file)</span></span>|-|<span data-ttu-id="05b58-125">指定基于目标的连接。</span><span class="sxs-lookup"><span data-stu-id="05b58-125">Specifies a destination-based connection.</span></span> <span data-ttu-id="05b58-126">SAP 连接参数包含在 saprfc.ini 文件中指定的目标。</span><span class="sxs-lookup"><span data-stu-id="05b58-126">The SAP connection parameters are contained in the specified destination in the saprfc.ini file.</span></span> <span data-ttu-id="05b58-127">目标中，可以指定仅类型 A 和 B 类型的连接。</span><span class="sxs-lookup"><span data-stu-id="05b58-127">Only TYPE A and TYPE B connections can be specified in the destination.</span></span> <span data-ttu-id="05b58-128">**注意：**如果 saprfc.ini 文件中指定的连接值，请确保该文件位于作为访问文件中的.exe 或在所需的 SAP 系统的标准位置的相同文件夹中。</span><span class="sxs-lookup"><span data-stu-id="05b58-128">**Note:**  If you specify connection values in the saprfc.ini file, make sure the file is located in the same folder as the .exe that accesses the file or at a standard location as required by the SAP system.</span></span> <span data-ttu-id="05b58-129">有关详细信息，请参阅 SAP 文档。</span><span class="sxs-lookup"><span data-stu-id="05b58-129">For more information, see the SAP documentation.</span></span>|  
  
 <span data-ttu-id="05b58-130">基于类型的连接，连接字符串以连接到 SAP 系统使用[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]可以包含以下属性。</span><span class="sxs-lookup"><span data-stu-id="05b58-130">Based on the type of connection, the connection string to connect to an SAP system using the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] can contain the following properties.</span></span>  
  
|<span data-ttu-id="05b58-131">属性</span><span class="sxs-lookup"><span data-stu-id="05b58-131">Property</span></span>|<span data-ttu-id="05b58-132">用于类型</span><span class="sxs-lookup"><span data-stu-id="05b58-132">Used for TYPE</span></span>|<span data-ttu-id="05b58-133">Description</span><span class="sxs-lookup"><span data-stu-id="05b58-133">Description</span></span>|  
|--------------|-------------------|-----------------|  
|<span data-ttu-id="05b58-134">应用程序服务器主机 (ASHOST)</span><span class="sxs-lookup"><span data-stu-id="05b58-134">Application Server Host (ASHOST)</span></span>|<span data-ttu-id="05b58-135">仅当辅助副本配置为使用手动故障转移模式，并且至少一个辅助副本当前与主要副本同步时，</span><span class="sxs-lookup"><span data-stu-id="05b58-135">A</span></span>|<span data-ttu-id="05b58-136">SAP 应用程序服务器主机的名称。</span><span class="sxs-lookup"><span data-stu-id="05b58-136">Name of the SAP application server host.</span></span>|  
|<span data-ttu-id="05b58-137">系统编号 (SYSNR)</span><span class="sxs-lookup"><span data-stu-id="05b58-137">System Number (SYSNR)</span></span>|<span data-ttu-id="05b58-138">仅当辅助副本配置为使用手动故障转移模式，并且至少一个辅助副本当前与主要副本同步时，</span><span class="sxs-lookup"><span data-stu-id="05b58-138">A</span></span>|<span data-ttu-id="05b58-139">SAP 系统编号</span><span class="sxs-lookup"><span data-stu-id="05b58-139">The SAP system number</span></span>|  
|<span data-ttu-id="05b58-140">应用程序服务器组名称 （组）</span><span class="sxs-lookup"><span data-stu-id="05b58-140">Application Server Group Name (GROUP)</span></span>|<span data-ttu-id="05b58-141">B</span><span class="sxs-lookup"><span data-stu-id="05b58-141">B</span></span>|<span data-ttu-id="05b58-142">SAP 服务器组的名称。</span><span class="sxs-lookup"><span data-stu-id="05b58-142">Name of the SAP server group.</span></span> <span data-ttu-id="05b58-143">这是在负载平衡连接的应用程序服务器的可选组。</span><span class="sxs-lookup"><span data-stu-id="05b58-143">This is an optional group of application servers in a load balancing connection.</span></span>|  
|<span data-ttu-id="05b58-144">消息服务器主机 (MSHOST)</span><span class="sxs-lookup"><span data-stu-id="05b58-144">Message Server Host (MSHOST)</span></span>|<span data-ttu-id="05b58-145">B</span><span class="sxs-lookup"><span data-stu-id="05b58-145">B</span></span>|<span data-ttu-id="05b58-146">SAP 消息服务器主机的名称</span><span class="sxs-lookup"><span data-stu-id="05b58-146">Name of the SAP message server host</span></span>|  
|<span data-ttu-id="05b58-147">消息服务器服务 (MSSERV)</span><span class="sxs-lookup"><span data-stu-id="05b58-147">Message Server Service (MSSERV)</span></span>|<span data-ttu-id="05b58-148">B</span><span class="sxs-lookup"><span data-stu-id="05b58-148">B</span></span>|<span data-ttu-id="05b58-149">名称中指定的 SAP 消息服务器服务的\<系统驱动器\>: \WINDOWS\system32\drivers\etc\services 文件。</span><span class="sxs-lookup"><span data-stu-id="05b58-149">Name of the SAP message server service as specified in the \<system drive\>:\WINDOWS\system32\drivers\etc\services file.</span></span> <span data-ttu-id="05b58-150">如果不指定一个值，[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]假定此项为"任意\</ 3 系统名称\>"。</span><span class="sxs-lookup"><span data-stu-id="05b58-150">If you do not specify a value, the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] assumes this to be "sapms\<R/3 system name\>".</span></span> <span data-ttu-id="05b58-151">例如，如果 / 3 系统名称是 DV1，则适配器会假定要"sapmsDV1"的消息服务器服务名称。</span><span class="sxs-lookup"><span data-stu-id="05b58-151">For example, if the R/3 system name is DV1, the adapter assumes the message server service name to be "sapmsDV1".</span></span><br /><br /> <span data-ttu-id="05b58-152">但是，如果服务文件中的项不同，你必须指定该值。</span><span class="sxs-lookup"><span data-stu-id="05b58-152">However, if the entry in the services file is different, you must specify that value.</span></span>|  
|<span data-ttu-id="05b58-153">/ 3 系统名称 (R3NAME)</span><span class="sxs-lookup"><span data-stu-id="05b58-153">R/3 System Name (R3NAME)</span></span>|<span data-ttu-id="05b58-154">B</span><span class="sxs-lookup"><span data-stu-id="05b58-154">B</span></span>|<span data-ttu-id="05b58-155">SAP / 3 名称中。</span><span class="sxs-lookup"><span data-stu-id="05b58-155">The SAP R/3 name.</span></span>|  
|<span data-ttu-id="05b58-156">目标 （目标）</span><span class="sxs-lookup"><span data-stu-id="05b58-156">Destination (DEST)</span></span>|<span data-ttu-id="05b58-157">D</span><span class="sxs-lookup"><span data-stu-id="05b58-157">D</span></span>|<span data-ttu-id="05b58-158">从 saprfc.ini 文件中选取的连接参数。</span><span class="sxs-lookup"><span data-stu-id="05b58-158">Picks the connection parameters from the saprfc.ini file.</span></span>|  
|<span data-ttu-id="05b58-159">客户端 （客户端）</span><span class="sxs-lookup"><span data-stu-id="05b58-159">Client (CLIENT)</span></span>|<span data-ttu-id="05b58-160">A、 B、 D</span><span class="sxs-lookup"><span data-stu-id="05b58-160">A,B,D</span></span>|<span data-ttu-id="05b58-161">SAP 客户端数</span><span class="sxs-lookup"><span data-stu-id="05b58-161">The SAP client number</span></span>|  
|<span data-ttu-id="05b58-162">语言 (Lang)</span><span class="sxs-lookup"><span data-stu-id="05b58-162">Language (Lang)</span></span>|<span data-ttu-id="05b58-163">A、 B、 D</span><span class="sxs-lookup"><span data-stu-id="05b58-163">A,B,D</span></span>|<span data-ttu-id="05b58-164">语言</span><span class="sxs-lookup"><span data-stu-id="05b58-164">Language</span></span>|  
|<span data-ttu-id="05b58-165">密码 （密码）</span><span class="sxs-lookup"><span data-stu-id="05b58-165">Password (PASSWD)</span></span>|<span data-ttu-id="05b58-166">A、 B、 D</span><span class="sxs-lookup"><span data-stu-id="05b58-166">A,B,D</span></span>|<span data-ttu-id="05b58-167">SAP 用户密码</span><span class="sxs-lookup"><span data-stu-id="05b58-167">The SAP user password</span></span>|  
|<span data-ttu-id="05b58-168">用户名 （用户）</span><span class="sxs-lookup"><span data-stu-id="05b58-168">Username (USER)</span></span>|<span data-ttu-id="05b58-169">A、 B、 D</span><span class="sxs-lookup"><span data-stu-id="05b58-169">A,B,D</span></span>|<span data-ttu-id="05b58-170">要连接到 SAP 系统的用户名</span><span class="sxs-lookup"><span data-stu-id="05b58-170">The user name to connect to an SAP system</span></span>|  
|<span data-ttu-id="05b58-171">启用调试 (AbapDebug) 的 SAP GUI</span><span class="sxs-lookup"><span data-stu-id="05b58-171">Enable SAP GUI debugging (AbapDebug)</span></span>|<span data-ttu-id="05b58-172">A、 B、 D</span><span class="sxs-lookup"><span data-stu-id="05b58-172">A,B,D</span></span>|<span data-ttu-id="05b58-173">可选参数，用于指定是否从调试的 ABAP[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]启用和适配器是否使用 SAP GUI 进行调试。</span><span class="sxs-lookup"><span data-stu-id="05b58-173">Optional parameter that specifies whether ABAP debugging from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] is enabled and whether the adapter uses the SAP GUI for debugging.</span></span> <span data-ttu-id="05b58-174">该值可以为 True 或 False;如果为 True，则启用 ABAP 调试，并且打开 SAP GUI。</span><span class="sxs-lookup"><span data-stu-id="05b58-174">The value can be True or False; if True, ABAP debugging is enabled and the SAP GUI is opened.</span></span> <span data-ttu-id="05b58-175">默认值为 False。</span><span class="sxs-lookup"><span data-stu-id="05b58-175">The default is False.</span></span>|  
|<span data-ttu-id="05b58-176">跟踪 RFC SDK(RfcSdkTrace)</span><span class="sxs-lookup"><span data-stu-id="05b58-176">Trace RFC SDK(RfcSdkTrace)</span></span>|<span data-ttu-id="05b58-177">A、 B、 D</span><span class="sxs-lookup"><span data-stu-id="05b58-177">A,B,D</span></span>|<span data-ttu-id="05b58-178">指定是否启用 RFC 库跟踪的可选参数。</span><span class="sxs-lookup"><span data-stu-id="05b58-178">Optional parameter that specifies whether RFC library tracing is enabled.</span></span> <span data-ttu-id="05b58-179">该值可以为 True 或 False;如果为 True，则启用 RFC 库跟踪。</span><span class="sxs-lookup"><span data-stu-id="05b58-179">The value can be True or False; if True, RFC Library tracing is enabled.</span></span> <span data-ttu-id="05b58-180">默认值为 False。</span><span class="sxs-lookup"><span data-stu-id="05b58-180">The default is False.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="05b58-181">在属性列中的括号内提供的值是必须同时提供通过编程解决方案连接 URI 指定的连接属性的名称。</span><span class="sxs-lookup"><span data-stu-id="05b58-181">The values provided within parentheses in the Property column are the name of the connection properties that must be specified while providing the connection URI through a programming solution.</span></span> <span data-ttu-id="05b58-182">但是，如果你使用 DDEX 插件或 SQL Server 导入和导出向导使用 ADO 接口，作为友好名称列出的连接属性。</span><span class="sxs-lookup"><span data-stu-id="05b58-182">However, if you are using the DDEX plug-in or SQL Server Import and Export wizard to use the ADO interface, the connection properties are listed as friendly names.</span></span>  
  
## <a name="example-connection-string-for-type-a"></a><span data-ttu-id="05b58-183">类型的示例连接字符串 A</span><span class="sxs-lookup"><span data-stu-id="05b58-183">Example Connection String for TYPE A</span></span>  
 <span data-ttu-id="05b58-184">键入一个示例连接字符串将如下所示：</span><span class="sxs-lookup"><span data-stu-id="05b58-184">An example connection string for TYPE A would look like:</span></span>  
  
```  
TYPE=A; ASHOST=SAPSERVER; SYSNR=00; CLIENT=800; LANG=EN; USER=YourUserName; PASSWD=YourPassword;  
```  
  
> [!NOTE]
>  <span data-ttu-id="05b58-185">默认情况下[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]始终会将连接字符串的键入 a.</span><span class="sxs-lookup"><span data-stu-id="05b58-185">By default the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] always considers the connection string to be of TYPE A.</span></span>  
  
## <a name="example-connection-string-for-type-b"></a><span data-ttu-id="05b58-186">为类型 B 的示例连接字符串</span><span class="sxs-lookup"><span data-stu-id="05b58-186">Example Connection String for TYPE B</span></span>  
 <span data-ttu-id="05b58-187">类型 B 的一个示例连接字符串将如下所示：</span><span class="sxs-lookup"><span data-stu-id="05b58-187">An example connection string for TYPE B would look like:</span></span>  
  
```  
TYPE=B; R3NAME=NAME1; GROUP=ADAPTER; MSHOST=MSSERVER; CLIENT=800; LANG=EN; USER=YourUserName; PASSWD=YourPassword;  
```  
  
## <a name="example-connection-string-for-type-d"></a><span data-ttu-id="05b58-188">类型 D 的示例连接字符串</span><span class="sxs-lookup"><span data-stu-id="05b58-188">Example Connection String for TYPE D</span></span>  
 <span data-ttu-id="05b58-189">类型 D 一个示例连接字符串将如下所示：</span><span class="sxs-lookup"><span data-stu-id="05b58-189">An example connection string for TYPE D would look like:</span></span>  
  
```  
TYPE=D; DEST=TESTSAPSRV; CLIENT=800; LANG=EN; USER=YourUserName; PASSWD=YourPassword;  
```  
  
 <span data-ttu-id="05b58-190">示例 saprfc.ini 文件类似于：</span><span class="sxs-lookup"><span data-stu-id="05b58-190">A sample saprfc.ini file resembles:</span></span>  
  
```  
DEST=TESTSAPSRV  
TYPE=A  
ASHOST=ADAPSAP47  
SYSNR=00  
```  
  
 <span data-ttu-id="05b58-191">Saprfc.ini 文件有关的详细信息，请参阅[http://go.microsoft.com/fwlink/?LinkId=91457](http://go.microsoft.com/fwlink/?LinkId=91457)。</span><span class="sxs-lookup"><span data-stu-id="05b58-191">For more information about the saprfc.ini file, see [http://go.microsoft.com/fwlink/?LinkId=91457](http://go.microsoft.com/fwlink/?LinkId=91457).</span></span>  
  
 <span data-ttu-id="05b58-192">所有三种连接类型的密码不能包含两个双引号。</span><span class="sxs-lookup"><span data-stu-id="05b58-192">The password for all three connection types must not contain double quotation marks.</span></span> <span data-ttu-id="05b58-193">但是，如果密码包含任何其他特殊字符，密码必须括在双引号内。</span><span class="sxs-lookup"><span data-stu-id="05b58-193">However, if the password contains any other special characters, the password must be enclosed within double quotation marks.</span></span> <span data-ttu-id="05b58-194">例如：</span><span class="sxs-lookup"><span data-stu-id="05b58-194">For example:</span></span>  
  
```  
ASHOST=SAPSERVER; SYSNR=00; CLIENT=800; LANG=EN; USER=YourUserName; PASSWD=",@/:;_ \\";  
```  
  
> [!IMPORTANT]
>  <span data-ttu-id="05b58-195">你必须为只能有一个连接类型 A、 B 或 d。 指定的连接参数例如，如果连接字符串中指定应用程序服务器主机，你必须指定消息服务器主机名或 R3NAME。</span><span class="sxs-lookup"><span data-stu-id="05b58-195">You must specify the connection parameters for only one connection TYPE A, B, or D. For example, if you specify the Application Server Host in the connection string, you must not specify a Message Server Host name or the R3NAME.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05b58-196">另请参阅</span><span class="sxs-lookup"><span data-stu-id="05b58-196">See Also</span></span>  
 [<span data-ttu-id="05b58-197">使用 mySAP Business Suite 的 .NET Framework 数据提供程序</span><span class="sxs-lookup"><span data-stu-id="05b58-197">Use the .NET Framework Data Provider for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md)