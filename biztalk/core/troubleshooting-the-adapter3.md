---
title: JD Edwards OneWorld 适配器疑难解答 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2dd6a951-f113-4f43-b43f-057a239d05c4
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4ac3c1d96de7faaf4200f9ee93387cc4a9a36933
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65306413"
---
# <a name="troubleshooting-the-adapter"></a>适配器疑难解答
本主题包含有助于您确定和解决使用用于 JD Edwards OneWorld 的 Microsoft BizTalk 适配器时可能遇到的问题的信息。  
  
## <a name="cannot-use-wildcards-in-send-and-receive-port-properties"></a>不能使用通配符在发送和接收端口属性  
 JD Edwards One World 的适配器不支持以下属性字段中使用通配符：  
  
|发送端口属性|接收端口属性|  
|------------------------|---------------------------|  
|用户名|事件文件路径|  
|JDE 环境|事件目标名称前缀|  
|主机||  
|Port||  
|Java_Home||  
|JDE JAR 文件||  
  
## <a name="connecting-to-oracle-database"></a>连接到 Oracle 数据库  
 与 JD Edwards 一起使用 Oracle 数据库时必须修改 jdeinterop.ini 文件。 使用单点登录 [JDBJ-ORACLE] 部分定义 Oracle tnsnames 位置;必须使用数据库参数;和 SQLNET。ORA 文件必须存在于 BizTalk Server 计算机 （这应为包含在 Oracle 客户端） 上。  
  
 以下代码添加到 jdeinterop.ini 文件：  
  
1.  在 [JDBJ-ORACLE] 下键入：  
  
    ```  
    tns=c:\Oracle\ora92\network\Admin\tnsnames.ora  
    ```  
  
2.  在 [JDBJ-BOOTSTRAP DATA SOURCE] 下键入：  
  
    ```  
    database=sys810 [hardcode the database name. This information is available in the JDE.ini file on the JD Edwards computer.]  
    ```  
  
## <a name="see-also"></a>请参阅  
 [将项目添加到 BizTalk 管理](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md)     
 [JD Edwards OneWorld 疑难解答](../core/troubleshooting-jd-edwards-oneworld.md)