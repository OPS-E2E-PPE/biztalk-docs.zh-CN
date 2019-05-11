---
title: 方案：分发在多台计算机之间的项目 |Microsoft Docs
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
ms.openlocfilehash: e64cdf9ac474697961d4f8fd41bb75057d27aa54
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65308322"
---
# <a name="scenario-distributing-artifacts-among-multiple-computers"></a>方案：分发在多台计算机之间的项目
本主题介绍应用程序部署方案时的应用程序中的项目有选择地安装在不同计算机上。 您可能想要执行此操作，如果您希望某些程序集或其他类型的项目中只能在 BizTalk 组中的特定计算机上安装的应用程序。 若要执行此操作，可以导出到多个.msi 文件，根据其项目要一起安装在物理计算机的应用程序中包含的项目。  
  
 下图显示了 BizTalk Group 1 导入 BizTalk 管理数据库的.msi 文件。 这将在该组中创建订单处理应用程序和所有项目。 然后，应用程序项目将导出到两个不同的.msi 文件。 一个.msi 文件包含 Assembly1、 Certificate1 和 Script1。 另一个.msi 文件包含 Assembly2、 Script2 和 VirtualDirectory1。  
  
 这两个.msi 文件导入到 BizTalk 组 2。 因为它们都属于 Order Processing 应用程序时，系统会将这两个.msi 文件中的项目的所有导入到名为新组中的订单处理同一应用程序。  
  
 此外，从到将运行这些组中的计算机上的.msi 文件安装应用程序项目。 请注意，将包含虚拟目录的.msi 文件安装在 BizTalk Server B 和 BizTalk Server C，它们都运行 IIS。  
  
 ![安装在不同的计算机上的项目](../core/media/distributionofartifacts.gif "DistributionOfArtifacts")  
  
## <a name="see-also"></a>请参阅  
 [应用程序部署和管理方案](../core/application-deployment-and-management-scenarios.md)   
 [如何导出 BizTalk 应用程序](../core/how-to-export-a-biztalk-application.md)   
 [如何导入 BizTalk 应用程序](../core/how-to-import-a-biztalk-application.md)   
 [如何安装 BizTalk 应用程序](../core/how-to-install-a-biztalk-application.md)