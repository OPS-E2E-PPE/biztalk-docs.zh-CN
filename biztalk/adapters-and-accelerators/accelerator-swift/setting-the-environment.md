---
title: 设置环境 |Microsoft Docs
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
ms.openlocfilehash: c2bcff19cb26482c566820956f93642887b43015
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530101"
---
# <a name="setting-the-environment"></a><span data-ttu-id="27b61-102">设置环境</span><span class="sxs-lookup"><span data-stu-id="27b61-102">Setting the Environment</span></span>
<span data-ttu-id="27b61-103">**若要设置的环境：**</span><span class="sxs-lookup"><span data-stu-id="27b61-103">**To set the environment:**</span></span>  
  
1.  <span data-ttu-id="27b61-104">请确保配置 SWIFT 消息程序包。</span><span class="sxs-lookup"><span data-stu-id="27b61-104">Make sure SWIFT Message Pack is configured.</span></span> <span data-ttu-id="27b61-105">请参阅 Swift 消息包文档配置相同。</span><span class="sxs-lookup"><span data-stu-id="27b61-105">Refer to the Swift Message Pack documentation to configure the same.</span></span>  
  
2.  <span data-ttu-id="27b61-106">运行 SQL 脚本*\<驱动器\>*: \Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tools\DataImport\CreateProceduresScript.sql。</span><span class="sxs-lookup"><span data-stu-id="27b61-106">Run the SQL script *\<drive\>*:\Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tools\DataImport\CreateProceduresScript.sql.</span></span> <span data-ttu-id="27b61-107">如果 Swift 和 MessagePack 配置 A4Swift 以外的数据库名称，请更改 sql 脚本中的数据库名称。</span><span class="sxs-lookup"><span data-stu-id="27b61-107">Change the database name in the sql script if the Swift and MessagePack are configured for database name other than A4Swift.</span></span>  
  
3.  <span data-ttu-id="27b61-108">将关键字"数据源"的值设置为计算机名和密钥作为数据库名称的"数据库"(为其配置 Swift 和 MessagePack) 文件中*\<驱动器\>*: \Program Files\Microsoft BizTalkAccelerator for SWIFT\SDK\Tools\DataImport\DataImport.exe.config。</span><span class="sxs-lookup"><span data-stu-id="27b61-108">Set the value of Key “datasource” as ComputerName and key “database” as database name (for which the Swift and MessagePack is configured) in the file *\<drive\>*:\Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tools\DataImport\DataImport.exe.config.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="27b61-109">数据输入的文件不应在 DataImport.exe 文件所在的同一文件夹中。</span><span class="sxs-lookup"><span data-stu-id="27b61-109">The data input file should not be in the same folder as the DataImport.exe file.</span></span>  
  
4.  <span data-ttu-id="27b61-110">运行数据导入实用工具，以导入 BICplusIBAN 和 SEPA 表中的数据。</span><span class="sxs-lookup"><span data-stu-id="27b61-110">Run the DataImport utility to import data in BICplusIBAN and SEPA tables.</span></span>