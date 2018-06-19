---
title: 有关 SAP 中的 SAPDiscoveredObjects.xml 文件 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SAPDiscoveredObjects.xml
- .NET Framework Data Provider for mySAP Business Suite
- Data Provider for SAP
- Visual Studio DDEX plug-in
ms.assetid: 46ef600d-57ae-4c42-94ce-3099e42482f1
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ba0c156e2ad6ab0fcbccb5ba7629f63b0aa490e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25960715"
---
# <a name="about-the-sapdiscoveredobjectsxml-file-in-sap"></a><span data-ttu-id="90e99-102">有关 SAP 中 SAPDiscoveredObjects.xml 文件</span><span class="sxs-lookup"><span data-stu-id="90e99-102">About the SAPDiscoveredObjects.xml File in SAP</span></span>
<span data-ttu-id="90e99-103">如果你选择安装[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]) 连同[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装，安装程序将 SAPDiscoveredObjects.xml 文件通常情况下的复制\<安装驱动器\>: \program 文件\Microsoft Shared\Adapters\SAP。</span><span class="sxs-lookup"><span data-stu-id="90e99-103">If you chose to install the [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]) along with the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] installation, the setup program copies the SAPDiscoveredObjects.xml file typically at \<installation drive\>:\Program Files\Common Files\Microsoft Shared\Adapters\SAP.</span></span> <span data-ttu-id="90e99-104">后的全新安装文件的内容[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]，如下所示。</span><span class="sxs-lookup"><span data-stu-id="90e99-104">The contents of the file, after a fresh installation of the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], resemble the following.</span></span>  
  
```  
<DiscoveredObjects>  
  <SAP>  
  </SAP>  
</DiscoveredObjects>  
```  
  
 <span data-ttu-id="90e99-105">SAPDiscoveredObjects.xml 文件的用途是存储发现使用的 SAP 对象 （表和 Rfc） [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] DDEX 插件。</span><span class="sxs-lookup"><span data-stu-id="90e99-105">The purpose of the SAPDiscoveredObjects.xml file is to store the SAP objects (tables and RFCs) that you discover using the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)][!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] DDEX plug-in.</span></span> <span data-ttu-id="90e99-106">一旦你已使用 DDEX 插件来添加更多的 SAP 对象，它们将添加到此 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="90e99-106">Once you have used the DDEX plug-in to add more SAP objects, they are added to this XML file.</span></span> <span data-ttu-id="90e99-107">类似如下所示的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="90e99-107">The XML file looks like this.</span></span>  
  
```  
<DiscoveredObjects>  
  <SAP>  
    <Server name="server_name" user="user_name" client="800" type="connection_type">  
      <Tables>  
        <Table>KNA1</Table>  
        <Table>KNAS</Table>  
        <Table>KNAT</Table>  
      </Tables>  
      <RFCs>  
        <RFC>CUSTOMER_CONTACTPS_GET</RFC>  
        <RFC>CUSTOMER_CONTROL_AREA_DATA</RFC>  
        <RFC>CUSTOMER_PARTNERFS_GET</RFC>  
      </RFCs>  
    </Server>  
  </SAP>  
</DiscoveredObjects>  
```  
  
 <span data-ttu-id="90e99-108">`name`属性 < 服务器\>元素包含连接到使用 DDEX 插件的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="90e99-108">The `name` property of the <Server\> element contains the name of the server that you connect to using the DDEX plug-in.</span></span> <span data-ttu-id="90e99-109">`user`和`client`属性 < 服务器\>元素分别包含的用户的名称和客户端编号。</span><span class="sxs-lookup"><span data-stu-id="90e99-109">The `user` and `client` properties of the <Server\> element contain the user name and client numbers, respectively.</span></span> <span data-ttu-id="90e99-110">`type`属性包含的一种用来连接到 SAP 系统的连接字符串 （A、 B 或 D）。</span><span class="sxs-lookup"><span data-stu-id="90e99-110">The `type` property contains the type of connection string (A, B, or D) used to connect to an SAP system.</span></span> <span data-ttu-id="90e99-111">有关类型的连接字符串的详细信息，请参阅[SAP 连接字符串中读取有关数据提供程序类型](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md)。</span><span class="sxs-lookup"><span data-stu-id="90e99-111">For more information about the types of connection strings, see [Read about Data Provider types for the SAP Connection String](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md).</span></span>  
  
 <span data-ttu-id="90e99-112">\<表\>元素包含您添加使用的插件的表的名称。</span><span class="sxs-lookup"><span data-stu-id="90e99-112">The \<Tables\> element contains the name of the tables that you add using the plug-in.</span></span> <span data-ttu-id="90e99-113">同样， \<Rfc\>元素包含使用插件添加了 Rfc。</span><span class="sxs-lookup"><span data-stu-id="90e99-113">Similarly, the \<RFCs\> element contains the RFCs that you add using the plug-in.</span></span> <span data-ttu-id="90e99-114">如果你连接到多个 SAP 服务器，另一个\<服务器\>元素添加到 XML 文件中，并且相应的表和 Rfc 列出在\<表\>和\<Rfc\>元素。</span><span class="sxs-lookup"><span data-stu-id="90e99-114">If you connect to more than one SAP server, another \<Server\> element is added to the XML file, and the corresponding tables and RFCs are listed under the \<Table\> and \<RFCs\> element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="90e99-115">有关使用插件的 Visual Studio DDEX 的说明，请参阅[数据提供程序用于与插件 DDEX SAP](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-with-the-ddex-plug-in.md)。</span><span class="sxs-lookup"><span data-stu-id="90e99-115">For instructions on using the Visual Studio DDEX plug-in, see [Use the Data Provider for SAP with the DDEX Plug-in](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-with-the-ddex-plug-in.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90e99-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="90e99-116">See Also</span></span>  
 [<span data-ttu-id="90e99-117">关于 mySAP Business Suite 的 .NET Framework 数据提供程序</span><span class="sxs-lookup"><span data-stu-id="90e99-117">About the .NET Framework Data Provider for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/about-the-net-framework-data-provider-for-mysap-business-suite.md)