---
title: 部署本地化 BAM XML 文件 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM, unicode mapping
- unicode mapping [BAM]
ms.assetid: 8e7e3431-cd20-45db-b7f2-0df23e9df42b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3452f13569ca6a0c0bb5843995c07a15b30f4da3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239309"
---
# <a name="deploying-localized-bam-xml-files"></a><span data-ttu-id="407ca-102">部署本地化的 BAM XML 文件</span><span class="sxs-lookup"><span data-stu-id="407ca-102">Deploying Localized BAM XML Files</span></span>
<span data-ttu-id="407ca-103">Microsoft SQL Server Analysis Services 支持 Unicode 映射。</span><span class="sxs-lookup"><span data-stu-id="407ca-103">Microsoft SQL Server Analysis Services supports Unicode mapping.</span></span> <span data-ttu-id="407ca-104">但是，对于 SQL Server Analysis Services 和 Visual Basic Unicode 映射，存在几个已知的字符出错问题。</span><span class="sxs-lookup"><span data-stu-id="407ca-104">However, there are known character corruption issues with SQL Server Analysis Services and Visual Basic Unicode mapping.</span></span> <span data-ttu-id="407ca-105">具体而言，在从 ANSI 转换为 Unicode 时，如果区域设置未设为正确的本地化语言，将使用错误的区域设置信息执行转换，从而导致出现字符错误。</span><span class="sxs-lookup"><span data-stu-id="407ca-105">Specifically, if the regional settings are not set to the correct localized language when the conversion from ANSI to Unicode occurs, the conversion is performed using the wrong locale information and character corruption occurs.</span></span>  
  
 <span data-ttu-id="407ca-106">若要成功部署 BAM 定义 XML 文件，必须先将系统区域设置切换为正确的区域设置，然后再实际部署包含本地化字符的 BAM 定义 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="407ca-106">To deploy the BAM definition XML file successfully, you must switch your system locale to the correct locale before you can actually deploy a BAM definition XML file that contains localized characters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="407ca-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="407ca-107">See Also</span></span>  
 <span data-ttu-id="407ca-108">[管理 BAM](../core/managing-bam.md) </span><span class="sxs-lookup"><span data-stu-id="407ca-108">[Managing BAM](../core/managing-bam.md) </span></span>  
 [<span data-ttu-id="407ca-109">BAM 管理实用工具</span><span class="sxs-lookup"><span data-stu-id="407ca-109">BAM Management Utility</span></span>](../core/bam-management-utility.md)