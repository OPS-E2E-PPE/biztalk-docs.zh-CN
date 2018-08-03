---
title: 将环境设置 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 43027efc-acec-4110-96bd-cc4a19daaeab
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f0c63671833a394e0c750561d90c12c6476515f
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25961891"
---
# <a name="setting-the-environment"></a><span data-ttu-id="c8b55-102">将环境设置</span><span class="sxs-lookup"><span data-stu-id="c8b55-102">Setting the Environment</span></span>
<span data-ttu-id="c8b55-103">**若要将环境设置：**</span><span class="sxs-lookup"><span data-stu-id="c8b55-103">**To set the environment:**</span></span>  
  
1.  <span data-ttu-id="c8b55-104">请确保配置 SWIFT 消息包。</span><span class="sxs-lookup"><span data-stu-id="c8b55-104">Make sure SWIFT Message Pack is configured.</span></span> <span data-ttu-id="c8b55-105">请参阅 Swift 消息包文档配置相同。</span><span class="sxs-lookup"><span data-stu-id="c8b55-105">Refer to the Swift Message Pack documentation to configure the same.</span></span>  
  
2.  <span data-ttu-id="c8b55-106">运行 SQL 脚本*\<驱动器\>*: files\microsoft BizTalk Accelerator for SWIFT\SDK\Tools\DataImport\CreateProceduresScript.sql。</span><span class="sxs-lookup"><span data-stu-id="c8b55-106">Run the SQL script *\<drive\>*:\Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tools\DataImport\CreateProceduresScript.sql.</span></span> <span data-ttu-id="c8b55-107">如果为 A4Swift 之外的数据库名称配置了 Swift 和 MessagePack，更改中的 sql 脚本的数据库名称。</span><span class="sxs-lookup"><span data-stu-id="c8b55-107">Change the database name in the sql script if the Swift and MessagePack are configured for database name other than A4Swift.</span></span>  
  
3.  <span data-ttu-id="c8b55-108">将键"数据源"的值设置为计算机名和密钥"数据库"作为数据库名称 (为其配置的 Swift 和 MessagePack) 文件中*\<驱动器\>*: files\microsoft BizTalkSWIFT\SDK\Tools\DataImport\DataImport.exe.config 快捷键。</span><span class="sxs-lookup"><span data-stu-id="c8b55-108">Set the value of Key “datasource” as ComputerName and key “database” as database name (for which the Swift and MessagePack is configured) in the file *\<drive\>*:\Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tools\DataImport\DataImport.exe.config.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c8b55-109">数据输入的文件不应在 DataImport.exe 文件所在的同一文件夹中。</span><span class="sxs-lookup"><span data-stu-id="c8b55-109">The data input file should not be in the same folder as the DataImport.exe file.</span></span>  
  
4.  <span data-ttu-id="c8b55-110">运行数据导入实用程序导入 BICplusIBAN 和 SEPA 表中的数据。</span><span class="sxs-lookup"><span data-stu-id="c8b55-110">Run the DataImport utility to import data in BICplusIBAN and SEPA tables.</span></span>