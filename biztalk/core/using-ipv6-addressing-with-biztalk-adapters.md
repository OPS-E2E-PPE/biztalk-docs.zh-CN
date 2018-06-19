---
title: 使用 IPv6 寻址与 BizTalk 适配器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 93cd2ead-5e87-47ac-8f78-d56b80afd34e
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e5726d5b05c548fd728228fcad39e56ce535fbb5
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2018
ms.locfileid: "29710620"
---
# <a name="using-ipv6-addressing-with-biztalk-adapters"></a><span data-ttu-id="94ac8-102">对 BizTalk 适配器使用 IPv6 寻址</span><span class="sxs-lookup"><span data-stu-id="94ac8-102">Using IPv6 Addressing with BizTalk Adapters</span></span>
<span data-ttu-id="94ac8-103">BizTalk Server 适配器支持使用 IPv6 寻址。</span><span class="sxs-lookup"><span data-stu-id="94ac8-103">BizTalk Server adapters support the use of IPv6 addressing.</span></span> <span data-ttu-id="94ac8-104">本主题介绍了指定 UNC 路径的 IPv6 地址时应当使用的命名法、指定文本 IPv6 地址时使用的命名法，以及如何对 HTTP 和 SOAP 适配器使用 IPv6 范围标识符。</span><span class="sxs-lookup"><span data-stu-id="94ac8-104">This topic describes the nomenclature that should be used to specify an IPv6 address for a UNC path, the nomenclature for specifying a literal IPv6 address, and the use of IPv6 scope identifiers with the HTTP and SOAP adapters.</span></span>  
  
## <a name="ipv6-address-nomenclature-used-for-a-unc-path"></a><span data-ttu-id="94ac8-105">用于 UNC 路径的 IPv6 地址命名法</span><span class="sxs-lookup"><span data-stu-id="94ac8-105">IPv6 Address Nomenclature Used for a UNC Path</span></span>  
 <span data-ttu-id="94ac8-106">如果在 UNC 路径中指定一个文本 IPv6 地址，请按照以下步骤进行操作：</span><span class="sxs-lookup"><span data-stu-id="94ac8-106">Follow these steps when specifying a literal IPv6 address in a UNC path:</span></span>  
  
1.  <span data-ttu-id="94ac8-107">使用短划线“-”字符替换任何冒号“:”字符。</span><span class="sxs-lookup"><span data-stu-id="94ac8-107">Replace any colon ":" characters with a dash "-" character.</span></span>  
  
2.  <span data-ttu-id="94ac8-108">将文本追加"**.ipv6 literal.net**"的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="94ac8-108">Append the text "**.ipv6-literal.net**" to the IP address.</span></span>  
  
 <span data-ttu-id="94ac8-109">例如，如果计算机的 IPv6 地址为 2001:DB8:2a:1005:230:48ff:fe73:989d，则指向该计算机上文件共享路径的 URI 的命名法为：</span><span class="sxs-lookup"><span data-stu-id="94ac8-109">For example, the nomenclature for a URI that points to a file share on a computer with the IPv6 address 2001:DB8:2a:1005:230:48ff:fe73:989d would be:</span></span>  
  
```  
\\2001-DB8-2a-1005-230-48ff-fe73-989d.ipv6-literal.net\<sharename\>  
```  
  
 <span data-ttu-id="94ac8-110">其中\< *sharename* \>是目标计算机上的文件共享的名称。</span><span class="sxs-lookup"><span data-stu-id="94ac8-110">Where \<*sharename*\> is the name of the file share on the target computer.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="94ac8-111">确保用于运行文件发送和接收处理程序的主机实例的用户帐户具有对该文件共享的相应权限。</span><span class="sxs-lookup"><span data-stu-id="94ac8-111">Ensure that the user accounts for the host instances that the File send and receive handlers are running in have appropriate permissions to the file share.</span></span> <span data-ttu-id="94ac8-112">有关与文件适配器接收文件所需的文件夹权限的详细信息请参阅[配置文件接收处理](../core/configure-the-file-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="94ac8-112">For more information about the folder permissions required to receive files with the File adapter see [Configure a File Receive Handler](../core/configure-the-file-adapter.md).</span></span> <span data-ttu-id="94ac8-113">有关所需时发送与文件适配器的文件的文件夹权限的详细信息请参阅[文件适配器的已知问题](../core/known-issues-with-the-file-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="94ac8-113">For more information about the folder permissions required when sending files with the File adapter see [Known Issues with the File Adapter](../core/known-issues-with-the-file-adapter.md).</span></span> <span data-ttu-id="94ac8-114">有关支持用于文件适配器的文件系统的信息，请参阅 [http://support.microsoft.com/kb/815070](http://support.microsoft.com/kb/815070)。</span><span class="sxs-lookup"><span data-stu-id="94ac8-114">For information about the file systems that are supported for use with the File adapter, see [http://support.microsoft.com/kb/815070](http://support.microsoft.com/kb/815070).</span></span>  
  
## <a name="using-ipv6-scope-identifiers-with-the-http-adapter-and-the-soap-send-adapter"></a><span data-ttu-id="94ac8-115">对 HTTP 适配器和 SOAP 发送适配器使用 IPv6 范围标识符</span><span class="sxs-lookup"><span data-stu-id="94ac8-115">Using IPv6 Scope Identifiers with the HTTP Adapter and the SOAP Send Adapter</span></span>  
 <span data-ttu-id="94ac8-116">HTTP 发送和接收适配器，并且 SOAP 发送适配器需要，如果 IPv6 地址中使用的范围标识符，则必须进行的作用域标识符转义替换为转义代码 **%25**。</span><span class="sxs-lookup"><span data-stu-id="94ac8-116">The HTTP send and receive adapter and the SOAP send adapter require that if a scope identifier is used in an IPv6 address, the scope identifier must be escaped with the escape code **%25**.</span></span> <span data-ttu-id="94ac8-117">例如， **fe80::550c:489f:e65e:aef3 %8** 是有效的 IPv6 地址包含作用域标识符 (%8)。</span><span class="sxs-lookup"><span data-stu-id="94ac8-117">For example, **fe80::550c:489f:e65e:aef3%8** is a valid IPv6 address containing a scope identifier (%8).</span></span> <span data-ttu-id="94ac8-118">若要将此 IPv6 地址用于 HTTP 发送和接收适配器或 SOAP 发送适配器，必须对该范围标识符进行转义，如下所示：</span><span class="sxs-lookup"><span data-stu-id="94ac8-118">To use this IPv6 address with the HTTP send and receive adapters or the SOAP send adapter, the scope identifier must be escaped as follows:</span></span>  
  
```  
fe80::550c:489f:e65e:aef3%258  
```  
  
## <a name="adapter-uri-nomenclature-used-for-a-literal-ipv6-address"></a><span data-ttu-id="94ac8-119">用于文本 IPv6 地址的适配器 URI 命名法</span><span class="sxs-lookup"><span data-stu-id="94ac8-119">Adapter URI Nomenclature Used for a Literal IPv6 Address</span></span>  
  
-   <span data-ttu-id="94ac8-120">若要将文本 IPv6 地址用于适配器 URI，请将 IP 地址两边括上方括号“[”、“]”。</span><span class="sxs-lookup"><span data-stu-id="94ac8-120">To use a literal IPv6 address for an adapter URI, enclose the IP address in square brackets "[", "]".</span></span> <span data-ttu-id="94ac8-121">例如，具有 IPv6 地址 2001:DB8:2a:1005:230:48ff:fe73:989d 的 URI 的命名法应为：</span><span class="sxs-lookup"><span data-stu-id="94ac8-121">For example, the nomenclature for a URI with the IPv6 address 2001:DB8:2a:1005:230:48ff:fe73:989d would be:</span></span>  
  
    ```  
    [2001:DB8:2a:1005:230:48ff:fe73:989d]  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="94ac8-122">文本使用 IPv6 地址的适配器 Uri 遵循在中建立的准则 [RFC2732](http://go.microsoft.com/fwlink/?LinkId=90375)。</span><span class="sxs-lookup"><span data-stu-id="94ac8-122">The use of literal IPv6 addresses for adapter URIs follows the guidelines established in [RFC2732](http://go.microsoft.com/fwlink/?LinkId=90375).</span></span>  
  
-   <span data-ttu-id="94ac8-123">如果指定文本 IPv6 地址作为用于 POP3 接收适配器、SMTP 发送适配器或 SQL 发送和接收适配器的服务器名，则 IPv6 地址不应用方括号括起来。</span><span class="sxs-lookup"><span data-stu-id="94ac8-123">When specifying a literal IPv6 address as the server name for the POP3 receive adapter, the SMTP send adapter, or the SQL send and receive adapters, the IPv6 address should not be enclosed in square brackets.</span></span>  
  
## <a name="summary-of-considerations-when-using-literal-ipv6-addressing-with-biztalk-adapters"></a><span data-ttu-id="94ac8-124">对 BizTalk 适配器使用文本 IPv6 寻址时的注意事项摘要</span><span class="sxs-lookup"><span data-stu-id="94ac8-124">Summary of Considerations When Using Literal IPv6 Addressing with BizTalk Adapters</span></span>  
 <span data-ttu-id="94ac8-125">下表简要列出了何时使用文本 IPv6 地址需要将 IP 地址用方括号“[”、“]”括起来，以及何时需要对用在 IPv6 地址中的范围标识符进行转义：</span><span class="sxs-lookup"><span data-stu-id="94ac8-125">The table below summarizes when the use of a literal IPv6 address requires that the IP address is enclosed in square brackets "[", "]" and when a scope identifier that is used in an IPv6 address must be escaped:</span></span>  
  
|<span data-ttu-id="94ac8-126">适配器</span><span class="sxs-lookup"><span data-stu-id="94ac8-126">Adapter</span></span>|<span data-ttu-id="94ac8-127">是否需要将文本 IPv6 地址用方括号括起来？</span><span class="sxs-lookup"><span data-stu-id="94ac8-127">Requires that literal IPv6 address is enclosed in square brackets?</span></span>|<span data-ttu-id="94ac8-128">是否需要对范围标识符进行转义？</span><span class="sxs-lookup"><span data-stu-id="94ac8-128">Requires that scope identifier is escaped?</span></span>|  
|---|---|---|  
|<span data-ttu-id="94ac8-129">POP3 接收</span><span class="sxs-lookup"><span data-stu-id="94ac8-129">POP3 receive</span></span>|<span data-ttu-id="94ac8-130">否</span><span class="sxs-lookup"><span data-stu-id="94ac8-130">No</span></span>|<span data-ttu-id="94ac8-131">否</span><span class="sxs-lookup"><span data-stu-id="94ac8-131">No</span></span>|  
|<span data-ttu-id="94ac8-132">SMTP 发送</span><span class="sxs-lookup"><span data-stu-id="94ac8-132">SMTP send</span></span>|<span data-ttu-id="94ac8-133">否</span><span class="sxs-lookup"><span data-stu-id="94ac8-133">No</span></span>|<span data-ttu-id="94ac8-134">否</span><span class="sxs-lookup"><span data-stu-id="94ac8-134">No</span></span>|  
|<span data-ttu-id="94ac8-135">SQL 发送和接收</span><span class="sxs-lookup"><span data-stu-id="94ac8-135">SQL send and receive</span></span>|<span data-ttu-id="94ac8-136">否</span><span class="sxs-lookup"><span data-stu-id="94ac8-136">No</span></span>|<span data-ttu-id="94ac8-137">否</span><span class="sxs-lookup"><span data-stu-id="94ac8-137">No</span></span>|  
|<span data-ttu-id="94ac8-138">文件发送和接收</span><span class="sxs-lookup"><span data-stu-id="94ac8-138">File send and receive</span></span>|<span data-ttu-id="94ac8-139">否 (请参阅部分 **IPv6 地址命名法使用 UNC 路径**)</span><span class="sxs-lookup"><span data-stu-id="94ac8-139">No (see section **IPv6 Address Nomenclature Used for a UNC Path**)</span></span>|<span data-ttu-id="94ac8-140">否</span><span class="sxs-lookup"><span data-stu-id="94ac8-140">No</span></span>|  
|<span data-ttu-id="94ac8-141">HTTP 发送和接收</span><span class="sxs-lookup"><span data-stu-id="94ac8-141">HTTP send and receive</span></span>|<span data-ttu-id="94ac8-142">是</span><span class="sxs-lookup"><span data-stu-id="94ac8-142">Yes</span></span>|<span data-ttu-id="94ac8-143">是</span><span class="sxs-lookup"><span data-stu-id="94ac8-143">Yes</span></span>|  
|<span data-ttu-id="94ac8-144">MQSeries 发送和接收</span><span class="sxs-lookup"><span data-stu-id="94ac8-144">MQSeries send and receive</span></span>|<span data-ttu-id="94ac8-145">是</span><span class="sxs-lookup"><span data-stu-id="94ac8-145">Yes</span></span>|<span data-ttu-id="94ac8-146">否</span><span class="sxs-lookup"><span data-stu-id="94ac8-146">No</span></span>|  
|<span data-ttu-id="94ac8-147">MSMQ 发送和接收</span><span class="sxs-lookup"><span data-stu-id="94ac8-147">MSMQ send and receive</span></span>|<span data-ttu-id="94ac8-148">是</span><span class="sxs-lookup"><span data-stu-id="94ac8-148">Yes</span></span>|<span data-ttu-id="94ac8-149">否</span><span class="sxs-lookup"><span data-stu-id="94ac8-149">No</span></span>|  
|<span data-ttu-id="94ac8-150">SOAP 发送</span><span class="sxs-lookup"><span data-stu-id="94ac8-150">SOAP send</span></span>|<span data-ttu-id="94ac8-151">是</span><span class="sxs-lookup"><span data-stu-id="94ac8-151">Yes</span></span>|<span data-ttu-id="94ac8-152">是</span><span class="sxs-lookup"><span data-stu-id="94ac8-152">Yes</span></span>|  
|<span data-ttu-id="94ac8-153">SOAP 接收</span><span class="sxs-lookup"><span data-stu-id="94ac8-153">SOAP receive</span></span>|<span data-ttu-id="94ac8-154">是</span><span class="sxs-lookup"><span data-stu-id="94ac8-154">Yes</span></span>|<span data-ttu-id="94ac8-155">否</span><span class="sxs-lookup"><span data-stu-id="94ac8-155">No</span></span>|  
|<span data-ttu-id="94ac8-156">WCF 发送和接收</span><span class="sxs-lookup"><span data-stu-id="94ac8-156">WCF send and receive</span></span>|<span data-ttu-id="94ac8-157">是</span><span class="sxs-lookup"><span data-stu-id="94ac8-157">Yes</span></span>|<span data-ttu-id="94ac8-158">否</span><span class="sxs-lookup"><span data-stu-id="94ac8-158">No</span></span>|