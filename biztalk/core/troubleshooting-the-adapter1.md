---
title: 解决博士 Edwards EnterpriseOne 适配器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f5a55e52-039a-4aea-8251-b697fd061ddc
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eac716a7567930509ebfd310cdaf9874286b349c
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
ms.locfileid: "24013124"
---
# <a name="troubleshooting-the-adapter"></a>故障排除适配器
本主题包含可帮助您标识和解决使用用于 JD Edwards EnterpriseOne 的 Microsoft BizTalk 适配器时可能遇到的问题的信息。  
  
## <a name="cannot-use-wildcards-in-send-port-properties"></a>无法在发送端口属性中使用通配符  
 用于 JD Edwards Enterprise One 的适配器不支持在以下发送端口属性字段中使用通配符：  
  
-   用户名  
  
-   JDE 环境  
  
-   主机  
  
-   端口  
  
-   Java_Home  
  
-   JDE JAR 文件  
  
-   安全服务器名称  
  
-   服务名称连接  
  
-   数据源名称  
  
-   数据库所有者  
  
-   数据库服务器名称  
  
-   数据库类型  
  
-   物理数据库名称  
  
## <a name="connecting-to-oracle-database"></a>连接到 Oracle 数据库  
 将 Oracle 数据库与 JD Edwards 一起使用时，必须修改 jdeinterop.ini 文件。 [JDBj-ORACLE] 部分使用单一登录功能定义 Oracle tnsnames 位置；必须使用数据库参数；BizTalk Server 计算机上必须存在 SQLNET.ORA 文件（此文件应包含在 Oracle 客户端）。  
  
 将以下内容添加到 jdeinterop.ini 文件：  
  
1.  在 [JDBj-ORACLE] 下：  
  
    ```  
    tns=c:\Oracle\ora92\network\Admin\tnsnames.ora  
    ```  
  
2.  在 [JDBj-BOOTSTRAP DATA SOURCE] 下：  
  
    ```  
    database=sys810 [hardcode the database name. This information is available in the JDE.ini file on the JD Edwards computer.]  
    ```  
  
## <a name="see-also"></a>另请参阅  
 [添加适配器，并创建项目](../core/adding-biztalk-adapter-for-jd-edwards-enterpriseone.md)   
 [故障排除博士 Edwards EnterpriseOne](../core/troubleshooting-jd-edwards-enterpriseone.md)