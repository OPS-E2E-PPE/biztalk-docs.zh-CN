---
title: 如何修改组属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- modifying, groups
- configuring, groups
- groups, configuring
- managing [groups], properties
- groups, modifying
- managing [groups], modifying
- groups, properties
ms.assetid: 59e0853d-81b0-43f9-85bf-099868e25fad
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4e654678caef42214ff4cb2df319830f9e96c073
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384598"
---
# <a name="how-to-modify-group-properties"></a>如何修改组属性
此过程可用于 BizTalk Server 组配置的全局属性，以便可以选择签名证书、 修改缓存刷新间隔，并确定 BizTalk Server 将如何处理大消息。 有关 BizTalk Server 组属性的详细信息，请参阅[BizTalk 组](../core/biztalk-groups.md)。  

## <a name="prerequisites"></a>先决条件  
 若要执行此过程，必须以 BizTalk Server Administrators 组的成员的身份登录。  

### <a name="to-configure-biztalk-group-properties"></a>若要配置 BizTalk 组属性  

1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  

2. 在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开 BizTalk 组，右键单击**BizTalk 组**，然后单击**属性**。  

3. 在中**组属性**对话框中，在**常规**选项卡上，执行以下操作：  


   |             使用此选项             |                                                                                                          执行的操作                                                                                                           |
   |----------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |             **名称**             | 键入组名称。 组名称不能超过 128 个字符的长度。 此框中的名称的旁边将出现**组**节点在控制台树中，以及服务器名称和 BizTalk 管理数据库名称。 |
   |            **Server**            |                                                                      显示以物理方式存储在 BizTalk 管理数据库的服务器。                                                                       |
   |           **“数据库”**           |                                                            显示为此组的设置存储所有配置的 BizTalk 管理数据库。                                                            |
   |       **SSO 服务器名称**        |       键入此计算机将使用存储和访问特定于适配器的信息的企业单一登录 (SSO) 服务器的名称。 这是用于连接到 SSO 数据库的 SSO 服务器的名称。       |
   | **BizTalk 管理员组**  |                                                  显示已安装后管理 BizTalk Server 环境的权限的管理员组的名称。                                                   |
   |   **BizTalk 操作员组**    |                                显示有权查看配置、 运行查询，以及执行计算机维护和基本应用程序监视操作员组的名称。                                |
   | **BizTalk Server B2B 操作员** |                                                                                         显示 B2B operators 组的名称。                                                                                         |


4. 上**数据库**选项卡上，执行以下操作：  


   |   使用此选项    |                                                           执行的操作                                                            |
   |---------------|---------------------------------------------------------------------------------------------------------------------------------|
   | **数据库** | 所有数据库的名称显示在应用程序和在其所驻留的服务器配置过程中指定。 |


5. 上**证书**选项卡上，执行以下操作，并单击**确定**:  

   |使用此选项|执行的操作|  
   |--------------|----------------|  
   |**公用名**|显示所选证书的说明。|  
   |**Thumbprint**|显示用于此组中的出站消息进行数字签名的私钥证书的指纹。 证书指纹的格式 HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH，其中 H 为十六进制数字 （从 0 到 9 的数字） 或为从 A 到 F 的字母。|  
   |**删除证书**|单击此项可删除所显示的证书。|  
   |**“浏览”**|单击此项可显示**选择证书**对话框中，在其中选择想要与组使用当前用户或个人存储区的签名证书。|  

## <a name="see-also"></a>请参阅  
 [管理组](../core/managing-groups.md)   
 [BizTalk 组](../core/biztalk-groups.md)   
 [如何将服务器添加到组](../core/how-to-add-a-server-to-a-group.md)   
 [如何将服务器从一个组移到另一个](../core/how-to-move-a-server-from-one-group-to-another.md)   
 [如何从一个组中删除服务器](../core/how-to-remove-a-server-from-a-group.md)