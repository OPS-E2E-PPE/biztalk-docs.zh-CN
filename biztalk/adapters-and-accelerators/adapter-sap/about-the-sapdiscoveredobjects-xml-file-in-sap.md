---
title: "有关 SAP 中的 SAPDiscoveredObjects.xml 文件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SAPDiscoveredObjects.xml
- .NET Framework Data Provider for mySAP Business Suite
- Data Provider for SAP
- Visual Studio DDEX plug-in
ms.assetid: 46ef600d-57ae-4c42-94ce-3099e42482f1
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 428d2987465ff1fe09f01979bbe9036def6350b8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="about-the-sapdiscoveredobjectsxml-file-in-sap"></a>有关 SAP 中 SAPDiscoveredObjects.xml 文件
如果你选择安装[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]) 连同[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装，安装程序将 SAPDiscoveredObjects.xml 文件通常情况下的复制\<安装驱动器 >: \program Files\MicrosoftShared\Adapters\SAP。 后的全新安装文件的内容[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]，如下所示。  
  
```  
<DiscoveredObjects>  
  <SAP>  
  </SAP>  
</DiscoveredObjects>  
```  
  
 SAPDiscoveredObjects.xml 文件的用途是存储发现使用的 SAP 对象 （表和 Rfc） [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] DDEX 插件。 一旦你已使用 DDEX 插件来添加更多的 SAP 对象，它们将添加到此 XML 文件。 类似如下所示的 XML 文件。  
  
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
  
 `name`属性 < 服务器\>元素包含连接到使用 DDEX 插件的服务器的名称。 `user`和`client`属性 < 服务器\>元素分别包含的用户的名称和客户端编号。 `type`属性包含的一种用来连接到 SAP 系统的连接字符串 （A、 B 或 D）。 有关类型的连接字符串的详细信息，请参阅[SAP 连接字符串中读取有关数据提供程序类型](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md)。  
  
 \<表 > 元素包含您添加使用的插件的表的名称。 同样， \<Rfc > 元素包含使用插件添加了 Rfc。 如果你连接到多个 SAP 服务器，另一个\<服务器 > 元素添加到 XML 文件中，并且相应的表和 Rfc 列出在\<表 > 和\<Rfc > 元素。  
  
> [!NOTE]
>  有关使用插件的 Visual Studio DDEX 的说明，请参阅[数据提供程序用于与插件 DDEX SAP](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-with-the-ddex-plug-in.md)。  
  
## <a name="see-also"></a>另请参阅  
 [有关.NET Framework 数据提供程序为 mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/about-the-net-framework-data-provider-for-mysap-business-suite.md)