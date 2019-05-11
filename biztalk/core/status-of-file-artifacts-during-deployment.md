---
title: 在部署过程中的文件项目的状态 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- artifacts, status
- deploying [artifacts], status
ms.assetid: 6d0f7336-c2cb-4aa4-9f1d-55fb85fe78bf
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c4f9abe5de90996d883a0c104985e30782a40188
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392923"
---
# <a name="status-of-file-artifacts-during-deployment"></a>在部署过程中的文件项目的状态
您可能需要知道当预处理或后处理脚本执行时，文件系统上存在哪些基于文件的项目。 例如，你可能想后处理脚本在卸载期间运行，并从文件系统中删除某个项目文件。 基于文件的项目是可以作为本地文件系统中，除了 BizTalk 数据库中的表示形式上的文件存在的项目。 基于文件的项目的示例包括 COM 组件、.NET 程序集、 BizTalk 程序集、 BAM 项目、 特别文件、 脚本和绑定文件。  
  
 下表总结了在部署过程中每个点的项目文件的状态。  
  
|在部署过程中点|应用程序项目文件的状态|  
|-------------------------------------|------------------------------------------|  
|预安装|只有 System.BizTalk.File 类型的文件存在于本地文件系统。|  
|安装后|所有文件都存在于本地文件系统。|  
|卸载前|所有文件都存在于本地文件系统。|  
|后卸载|尚未从本地文件系统中删除所有的文件。|  
|预导入|除非已在本地计算机上安装应用程序，没有文件存在于本地文件系统上。|  
|导入|除非已在本地计算机上安装应用程序，没有文件存在于本地文件系统上。|  
  
 \* 本地文件系统上的文件存在，仅当文件添加到应用程序时指定了有效的目标位置。  
  
## <a name="see-also"></a>请参阅  
 [使用预处理脚本和后期处理脚本自定义应用程序部署](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md)