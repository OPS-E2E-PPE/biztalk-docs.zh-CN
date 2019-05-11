---
title: 将连接到 BizTalk Server 与 SQL Server Always Encrypted 列 |Microsoft Docs
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
ms.openlocfilehash: a6d280bfc0ad199199c2963447c738e83e48c0d6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354931"
---
# <a name="connect-to-sql-server-always-encrypted-columns-with-biztalk-server"></a>将连接到 BizTalk Server 与 SQL Server Always Encrypted 列
中的 WCF SQL 适配器中启用始终加密[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]若要查询加密的列。  

**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** ，WCF SQL 适配器可以查询加密的列中[!INCLUDE[btsSQLServerNoVersion_md](../includes/btssqlservernoversion-md.md)]。 `ColumnEncryptionSetting`绑定属性用于启用或禁用 Always Encrypted 的数据库中获取解密/加密列的值的功能。

本主题演示如何启用或禁用此功能的[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]。

> [!TIP]
> [始终加密 （数据库引擎）](https://docs.microsoft.com/sql/relational-databases/security/encryption/always-encrypted-database-engine)是一个不错的资源以了解并了解有关这个[!INCLUDE[btsSQLServerNoVersion_md](../includes/btssqlservernoversion-md.md)]功能。

## <a name="prerequisites"></a>先决条件
安装[功能包 2](https://aka.ms/bts2016fp2)上你[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]。

## <a name="enable-always-encrypted"></a>启用始终加密

1. 在中**BizTalk Server 管理**控制台中，右键单击您的 WCF SQL 端口，并选择**属性**。
2. 转到**绑定**选项卡。
3. 下**Always Encrypted**、 启用或禁用`ColumnEncryptionSettings`属性：

* **启用**:端口查询和获取始终加密数据库中的加密的数据
* **已禁用**:端口查询的始终加密数据库，但返回的数据进行哈希运算

    ![启用始终加密](../core/media/enable-always-encrypted.png)

4. 选择**Apply**，并**确定**以保存所做的更改。

## <a name="see-also"></a>另请参阅
[Always Encrypted（数据库引擎）](https://docs.microsoft.com/sql/relational-databases/security/encryption/always-encrypted-database-engine)  
[配置功能包](../core/configure-the-feature-pack.md)