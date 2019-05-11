---
title: 部署已本地化的 BAM XML 文件 |Microsoft Docs
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
ms.openlocfilehash: 36eafa1c29da4b470710f2957d501bc9b91ccd98
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65352069"
---
# <a name="deploying-localized-bam-xml-files"></a>部署已本地化的 BAM XML 文件
Microsoft SQL Server Analysis Services 支持 Unicode 映射。 但是，对于 SQL Server Analysis Services 和 Visual Basic Unicode 映射，存在几个已知的字符出错问题。 具体而言，在从 ANSI 转换为 Unicode 时，如果区域设置未设为正确的本地化语言，将使用错误的区域设置信息执行转换，从而导致出现字符错误。  
  
 若要成功部署 BAM 定义 XML 文件，必须先将系统区域设置切换为正确的区域设置，然后再实际部署包含本地化字符的 BAM 定义 XML 文件。  
  
## <a name="see-also"></a>请参阅  
 [管理 BAM](../core/managing-bam.md)   
 [BAM 管理实用工具](../core/bam-management-utility.md)