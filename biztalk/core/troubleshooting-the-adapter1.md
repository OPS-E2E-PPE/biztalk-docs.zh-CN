---
title: JD Edwards EnterpriseOne 适配器疑难解答 |Microsoft Docs
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
ms.openlocfilehash: 1d6ba3fdb8789f7d258291aee05d9e7b481e905a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65306394"
---
# <a name="troubleshooting-the-adapter"></a>适配器疑难解答
本主题包含有助于您确定和解决使用用于 JD Edwards EnterpriseOne 的 Microsoft BizTalk 适配器时可能遇到的问题的信息。  
  
## <a name="cannot-use-wildcards-in-send-port-properties"></a>不能在发送端口属性中使用通配符  
 用于 JD Edwards Enterprise One 适配器不支持在以下发送端口属性字段中使用通配符：  
  
-   用户名  
  
-   JDE 环境  
  
-   主机  
  
-   Port  
  
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
 与 JD Edwards 一起使用 Oracle 数据库时必须修改 jdeinterop.ini 文件。 使用单点登录 [JDBJ-ORACLE] 部分定义 Oracle tnsnames 位置;必须使用数据库参数;和 SQLNET。ORA 文件必须存在于 BizTalk Server 计算机 （这应为包含在 Oracle 客户端） 上。  
  
 以下代码添加到 jdeinterop.ini 文件：  
  
1.  在 [JDBJ-ORACLE]:  
  
    ```  
    tns=c:\Oracle\ora92\network\Admin\tnsnames.ora  
    ```  
  
2.  在 [JDBJ-BOOTSTRAP DATA SOURCE]:  
  
    ```  
    database=sys810 [hardcode the database name. This information is available in the JDE.ini file on the JD Edwards computer.]  
    ```  
  
## <a name="see-also"></a>请参阅  
 [添加适配器，并创建项目](../core/adding-biztalk-adapter-for-jd-edwards-enterpriseone.md)   
 [Troubleshooting JD Edwards EnterpriseOne](../core/troubleshooting-jd-edwards-enterpriseone.md)