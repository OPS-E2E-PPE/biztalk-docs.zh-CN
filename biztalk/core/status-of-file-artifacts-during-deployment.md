---
title: 在部署过程中的文件项目的状态 |Microsoft 文档
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
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1f57716741bb61c7a9f6f012aed14ec04c8e250
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="status-of-file-artifacts-during-deployment"></a>在部署过程中的文件项目的状态
您可能需要知道，在执行预处理和后处理脚本时，文件系统上存在哪些基于文件的项目。 例如，您可能需要后处理脚本在卸载期间运行，并从文件系统中删除某个项目文件。 基于文件的项目是除了 BizTalk 数据库中的表示形式，还可以作为本地文件系统上的文件存在的项目。 基于文件的项目的示例包括：COM 组件、.NET 程序集、BizTalk 程序集、BAM 项目、特别文件、脚本和绑定文件。  
  
 下表概括了部署过程中的每个点的项目文件的状态。  
  
|部署过程中的点|应用程序项目文件的状态|  
|-------------------------------------|------------------------------------------|  
|安装前|只有 System.BizTalk.File 类型的文件在本地文件系统上存在。*|  
|安装后|所有文件均在本地文件系统上存在。*|  
|卸载前|所有文件均在本地文件系统上存在。*|  
|后卸载|所有文件已从本地文件系统中删除。|  
|导入前|直到在本地计算机上安装应用程序之后，本地文件系统上才存在文件。|  
|导入后|直到在本地计算机上安装应用程序之后，本地文件系统上才存在文件。|  
  
 \* 仅当该文件添加到应用程序时指定了有效的目标位置，本地文件系统上存在文件。  
  
## <a name="see-also"></a>另请参阅  
 [使用预处理脚本和后期处理脚本自定义应用程序部署](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md)