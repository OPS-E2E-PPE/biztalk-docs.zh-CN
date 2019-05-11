---
title: 有关 SAP 在 SAPDiscoveredObjects.xml 文件 |Microsoft Docs
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
ms.openlocfilehash: 7aba687a976ed67ce58727c4074fae526832ba17
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65374202"
---
# <a name="about-the-sapdiscoveredobjectsxml-file-in-sap"></a>有关 SAP 在 SAPDiscoveredObjects.xml 文件
如果您选择安装[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]) 连同[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装，安装程序将复制通常在 SAPDiscoveredObjects.xml 文件\<安装驱动器\>: \Program Files\Common 文件\Microsoft Shared\Adapters\SAP。 后的全新安装文件的内容[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]，如下所示。  
  
```  
<DiscoveredObjects>  
  <SAP>  
  </SAP>  
</DiscoveredObjects>  
```  
  
 在 SAPDiscoveredObjects.xml 文件的用途是存储发现使用的 SAP 对象 （表和 Rfc） [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] DDEX 插件。 一旦已使用的 DDEX 插件添加更多的 SAP 对象，它们会添加到此 XML 文件。 XML 文件如下所示。  
  
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
  
 `name`属性的 < 服务器\>元素包含使用 DDEX 插件连接到服务器的名称。 `user`并`client`的属性 < 服务器\>元素分别包含用户的名称和客户端数量。 `type`属性包含用来连接到 SAP 系统的连接字符串 （A、 B 或 D） 的类型。 有关连接字符串的类型的详细信息，请参阅[了解数据提供程序类型适用于 SAP 连接字符串](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md)。  
  
 \<表\>元素包含使用该插件添加的表的名称。 同样， \<Rfc\>元素包含将使用该插件的 Rfc。 如果连接到多个 SAP 服务器，另一个\<服务器\>元素添加到 XML 文件中，并且相应的表和 Rfc 下列出\<表\>并\<Rfc\>元素。  
  
> [!NOTE]
>  有关使用 Visual Studio DDEX 插件的说明，请参阅[使用包含 DDEX 插件的 SAP 数据提供程序](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-with-the-ddex-plug-in.md)。  
  
## <a name="see-also"></a>请参阅  
 [关于 mySAP Business Suite 的 .NET Framework 数据提供程序](../../adapters-and-accelerators/adapter-sap/about-the-net-framework-data-provider-for-mysap-business-suite.md)