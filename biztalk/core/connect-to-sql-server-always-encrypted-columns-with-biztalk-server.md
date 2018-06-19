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
# <a name="connect-to-sql-server-always-encrypted-columns-with-biztalk-server"></a><span data-ttu-id="e9cba-102">将连接到 SQL Server 始终加密的列与 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="e9cba-102">Connect to SQL Server Always Encrypted columns with BizTalk Server</span></span>
<span data-ttu-id="e9cba-103">启用始终加密中的 WCF SQL 适配器中[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]查询加密的列。</span><span class="sxs-lookup"><span data-stu-id="e9cba-103">Enable Always Encrypted in the WCF-SQL adapter in [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] to query encrypted columns.</span></span>  

<span data-ttu-id="e9cba-104">**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** ，WCF SQL 适配器可以查询加密的列中[!INCLUDE[btsSQLServerNoVersion_md](../includes/btssqlservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e9cba-104">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]**, the WCF-SQL adapter can query encrypted columns in [!INCLUDE[btsSQLServerNoVersion_md](../includes/btssqlservernoversion-md.md)].</span></span> <span data-ttu-id="e9cba-105">`ColumnEncryptionSetting`绑定属性用于启用或禁用始终加密数据库中获取解密/加密列的值的功能。</span><span class="sxs-lookup"><span data-stu-id="e9cba-105">The `ColumnEncryptionSetting` binding property is used to enable or disable the functionality to get decrypted/encrypted column values from an Always Encrypted database.</span></span>

<span data-ttu-id="e9cba-106">本主题演示如何启用或禁用此功能的[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e9cba-106">This topic shows you how to enable or disable this feature in [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span>

> [!TIP] 
> <span data-ttu-id="e9cba-107">[始终加密 （数据库引擎）](https://docs.microsoft.com/sql/relational-databases/security/encryption/always-encrypted-database-engine)是一个很好的资源，若要了解并了解有关这个[!INCLUDE[btsSQLServerNoVersion_md](../includes/btssqlservernoversion-md.md)]功能。</span><span class="sxs-lookup"><span data-stu-id="e9cba-107">[Always Encrypted (Database Engine)](https://docs.microsoft.com/sql/relational-databases/security/encryption/always-encrypted-database-engine) is a great resource to understand and learn more about this [!INCLUDE[btsSQLServerNoVersion_md](../includes/btssqlservernoversion-md.md)] feature.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e9cba-108">先决条件</span><span class="sxs-lookup"><span data-stu-id="e9cba-108">Prerequisites</span></span>
<span data-ttu-id="e9cba-109">安装[功能包 2](https://aka.ms/bts2016fp2)上你[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e9cba-109">Install [Feature Pack 2](https://aka.ms/bts2016fp2) on your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span>

## <a name="enable-always-encrypted"></a><span data-ttu-id="e9cba-110">启用始终加密</span><span class="sxs-lookup"><span data-stu-id="e9cba-110">Enable Always Encrypted</span></span>

1. <span data-ttu-id="e9cba-111">在**BizTalk Server 管理**控制台，右键单击您的 WCF SQL 端口，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="e9cba-111">In the **BizTalk Server Administration** console, right-click your WCF-SQL port, and select **Properties**.</span></span>
2. <span data-ttu-id="e9cba-112">转到**绑定**选项卡。</span><span class="sxs-lookup"><span data-stu-id="e9cba-112">Go to the **Binding** tab.</span></span>
3. <span data-ttu-id="e9cba-113">下**始终加密**、 启用或禁用`ColumnEncryptionSettings`属性：</span><span class="sxs-lookup"><span data-stu-id="e9cba-113">Under **Always Encrypted**, enable or disable the `ColumnEncryptionSettings` property:</span></span>

* <span data-ttu-id="e9cba-114">**启用**： 端口查询和获取始终加密数据库中的加密的数据</span><span class="sxs-lookup"><span data-stu-id="e9cba-114">**Enabled**: The port queries, and gets encrypted data from an Always Encrypted database</span></span>
* <span data-ttu-id="e9cba-115">**已禁用**: 端口查询的始终加密的数据库，但返回的数据进行哈希处理</span><span class="sxs-lookup"><span data-stu-id="e9cba-115">**Disabled**: The port queries the Always Encrypted database, but the data returned is hashed</span></span>

    ![启用始终加密](../core/media/enable-always-encrypted.png)

4. <span data-ttu-id="e9cba-117">选择**应用**，和**确定**以保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="e9cba-117">Select **Apply**, and **OK** to save your changes.</span></span>

## <a name="see-also"></a><span data-ttu-id="e9cba-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e9cba-118">See also</span></span>
[<span data-ttu-id="e9cba-119">始终加密（数据库引擎）</span><span class="sxs-lookup"><span data-stu-id="e9cba-119">Always Encrypted (Database Engine)</span></span>](https://docs.microsoft.com/sql/relational-databases/security/encryption/always-encrypted-database-engine)  
[<span data-ttu-id="e9cba-120">配置功能包</span><span class="sxs-lookup"><span data-stu-id="e9cba-120">Configure the Feature Pack</span></span>](../core/configure-the-feature-pack.md)