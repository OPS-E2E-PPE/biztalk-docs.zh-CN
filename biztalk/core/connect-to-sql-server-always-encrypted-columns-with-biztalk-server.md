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
# <a name="connect-to-sql-server-always-encrypted-columns-with-biztalk-server"></a><span data-ttu-id="f90da-102">将连接到 BizTalk Server 与 SQL Server Always Encrypted 列</span><span class="sxs-lookup"><span data-stu-id="f90da-102">Connect to SQL Server Always Encrypted columns with BizTalk Server</span></span>
<span data-ttu-id="f90da-103">中的 WCF SQL 适配器中启用始终加密[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]若要查询加密的列。</span><span class="sxs-lookup"><span data-stu-id="f90da-103">Enable Always Encrypted in the WCF-SQL adapter in [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] to query encrypted columns.</span></span>  

<span data-ttu-id="f90da-104">**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** ，WCF SQL 适配器可以查询加密的列中[!INCLUDE[btsSQLServerNoVersion_md](../includes/btssqlservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="f90da-104">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]**, the WCF-SQL adapter can query encrypted columns in [!INCLUDE[btsSQLServerNoVersion_md](../includes/btssqlservernoversion-md.md)].</span></span> <span data-ttu-id="f90da-105">`ColumnEncryptionSetting`绑定属性用于启用或禁用 Always Encrypted 的数据库中获取解密/加密列的值的功能。</span><span class="sxs-lookup"><span data-stu-id="f90da-105">The `ColumnEncryptionSetting` binding property is used to enable or disable the functionality to get decrypted/encrypted column values from an Always Encrypted database.</span></span>

<span data-ttu-id="f90da-106">本主题演示如何启用或禁用此功能的[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="f90da-106">This topic shows you how to enable or disable this feature in [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span>

> [!TIP]
> <span data-ttu-id="f90da-107">[始终加密 （数据库引擎）](https://docs.microsoft.com/sql/relational-databases/security/encryption/always-encrypted-database-engine)是一个不错的资源以了解并了解有关这个[!INCLUDE[btsSQLServerNoVersion_md](../includes/btssqlservernoversion-md.md)]功能。</span><span class="sxs-lookup"><span data-stu-id="f90da-107">[Always Encrypted (Database Engine)](https://docs.microsoft.com/sql/relational-databases/security/encryption/always-encrypted-database-engine) is a great resource to understand and learn more about this [!INCLUDE[btsSQLServerNoVersion_md](../includes/btssqlservernoversion-md.md)] feature.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f90da-108">先决条件</span><span class="sxs-lookup"><span data-stu-id="f90da-108">Prerequisites</span></span>
<span data-ttu-id="f90da-109">安装[功能包 2](https://aka.ms/bts2016fp2)上你[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="f90da-109">Install [Feature Pack 2](https://aka.ms/bts2016fp2) on your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span>

## <a name="enable-always-encrypted"></a><span data-ttu-id="f90da-110">启用始终加密</span><span class="sxs-lookup"><span data-stu-id="f90da-110">Enable Always Encrypted</span></span>

1. <span data-ttu-id="f90da-111">在中**BizTalk Server 管理**控制台中，右键单击您的 WCF SQL 端口，并选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="f90da-111">In the **BizTalk Server Administration** console, right-click your WCF-SQL port, and select **Properties**.</span></span>
2. <span data-ttu-id="f90da-112">转到**绑定**选项卡。</span><span class="sxs-lookup"><span data-stu-id="f90da-112">Go to the **Binding** tab.</span></span>
3. <span data-ttu-id="f90da-113">下**Always Encrypted**、 启用或禁用`ColumnEncryptionSettings`属性：</span><span class="sxs-lookup"><span data-stu-id="f90da-113">Under **Always Encrypted**, enable or disable the `ColumnEncryptionSettings` property:</span></span>

* <span data-ttu-id="f90da-114">**启用**:端口查询和获取始终加密数据库中的加密的数据</span><span class="sxs-lookup"><span data-stu-id="f90da-114">**Enabled**: The port queries, and gets encrypted data from an Always Encrypted database</span></span>
* <span data-ttu-id="f90da-115">**已禁用**:端口查询的始终加密数据库，但返回的数据进行哈希运算</span><span class="sxs-lookup"><span data-stu-id="f90da-115">**Disabled**: The port queries the Always Encrypted database, but the data returned is hashed</span></span>

    ![启用始终加密](../core/media/enable-always-encrypted.png)

4. <span data-ttu-id="f90da-117">选择**Apply**，并**确定**以保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="f90da-117">Select **Apply**, and **OK** to save your changes.</span></span>

## <a name="see-also"></a><span data-ttu-id="f90da-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f90da-118">See also</span></span>
[<span data-ttu-id="f90da-119">Always Encrypted（数据库引擎）</span><span class="sxs-lookup"><span data-stu-id="f90da-119">Always Encrypted (Database Engine)</span></span>](https://docs.microsoft.com/sql/relational-databases/security/encryption/always-encrypted-database-engine)  
[<span data-ttu-id="f90da-120">配置功能包</span><span class="sxs-lookup"><span data-stu-id="f90da-120">Configure the Feature Pack</span></span>](../core/configure-the-feature-pack.md)