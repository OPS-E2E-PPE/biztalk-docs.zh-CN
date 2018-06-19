---
title: 将连接到 SQL Server 始终加密的列与 BizTalk Server |Microsoft 文档
ms.custom: ''
ms.date: 11/20/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fcc20a2b-daf9-4b7f-ae61-cb408e4bd04c
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d5e117bd91176589e998fc01eb2c613ac0da2bbc
ms.sourcegitcommit: f65e8ed2b8c18cded26b9d60868fb6a56bcc1205
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
ms.locfileid: "25497743"
---
# <a name="connect-to-sql-server-always-encrypted-columns-with-biztalk-server"></a>将连接到 SQL Server 始终加密的列与 BizTalk Server
启用始终加密中的 WCF SQL 适配器中[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]查询加密的列。  

**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** ，WCF SQL 适配器可以查询加密的列中[!INCLUDE[btsSQLServerNoVersion_md](../includes/btssqlservernoversion-md.md)]。 `ColumnEncryptionSetting`绑定属性用于启用或禁用始终加密数据库中获取解密/加密列的值的功能。

本主题演示如何启用或禁用此功能的[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]。

> [!TIP] 
> [始终加密 （数据库引擎）](https://docs.microsoft.com/sql/relational-databases/security/encryption/always-encrypted-database-engine)是一个很好的资源，若要了解并了解有关这个[!INCLUDE[btsSQLServerNoVersion_md](../includes/btssqlservernoversion-md.md)]功能。

## <a name="prerequisites"></a>先决条件
安装[功能包 2](https://aka.ms/bts2016fp2)上你[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]。

## <a name="enable-always-encrypted"></a>启用始终加密

1. 在**BizTalk Server 管理**控制台，右键单击您的 WCF SQL 端口，然后选择**属性**。
2. 转到**绑定**选项卡。
3. 下**始终加密**、 启用或禁用`ColumnEncryptionSettings`属性：

* **启用**： 端口查询和获取始终加密数据库中的加密的数据
* **已禁用**: 端口查询的始终加密的数据库，但返回的数据进行哈希处理

    ![启用始终加密](../core/media/enable-always-encrypted.png)

4. 选择**应用**，和**确定**以保存所做的更改。

## <a name="see-also"></a>另请参阅
[始终加密（数据库引擎）](https://docs.microsoft.com/sql/relational-databases/security/encryption/always-encrypted-database-engine)  
[配置功能包](../core/configure-the-feature-pack.md)