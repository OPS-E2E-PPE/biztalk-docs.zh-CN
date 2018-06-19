---
title: 方案： 分发在多台计算机之间的项目 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying [artifacts], multiple computers
- examples, distributing
- examples, artifacts
- artifacts, distributing
- artifacts, examples
- deploying [artifacts], examples
- examples, deploying
ms.assetid: 7000cded-1fda-4276-b7f3-3f427f686f64
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: abedc60ad13c7e8b2be3ce4caa7b8d34262b4e5c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269157"
---
# <a name="scenario-distributing-artifacts-among-multiple-computers"></a>方案： 分发在多台计算机之间的项目
本主题将说明应用程序中的项目有选择地安装在不同计算机上时采用的应用程序部署方案。 如果您希望应用程序中的某些程序集或其他类型的项目只安装在 BizTalk 组中特定的计算机上，就会需要这种部署方案。 为此，您可以根据要在某个物理计算机上一起安装哪些项目，将应用程序中包括的项目导出到多个 .msi 文件。  
  
 下图显示导入到 BizTalk 管理数据库的 BizTalk 组 1 的.msi 文件。 这将该组中创建订单处理应用程序和所有其项目。 然后，应用程序项目导出到两个不同的 .msi 文件中。 一个 .msi 文件包含 Assembly1、Certificate1 和 Script1。 另一个 .msi 文件包含 Assembly2、Script2 和 VirtualDirectory1。  
  
 这两个.msi 文件导入到 BizTalk 组 2。 因为它们都属于订单处理应用程序时，系统会将这两个.msi 文件中的项目的所有导入到名为新组中的 Order Processing 相同应用程序。  
  
 此外，应用程序项目从 .msi 文件安装到该组中将运行它们的计算机上。 注意，包含虚拟目录的 .msi 文件安装在 BizTalk Server B 和 BizTalk Server C，它们都运行 IIS。  
  
 ![在不同计算机上安装的项目](../core/media/distributionofartifacts.gif "DistributionOfArtifacts")  
  
## <a name="see-also"></a>另请参阅  
 [应用程序部署和管理方案](../core/application-deployment-and-management-scenarios.md)   
 [如何导出 BizTalk 应用程序](../core/how-to-export-a-biztalk-application.md)   
 [如何导入 BizTalk 应用程序](../core/how-to-import-a-biztalk-application.md)   
 [如何安装 BizTalk 应用程序](../core/how-to-install-a-biztalk-application.md)