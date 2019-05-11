---
title: 配置客户端绑定适用于 Oracle E-business Suite |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1347cbca-5567-43f8-a75e-a23b108692bc
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8c05dadb7265a555a4162b73351b3783203f203d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375727"
---
# <a name="configure-a-client-binding-for-the-oracle-e-business-suite"></a>配置客户端绑定适用于 Oracle E-business Suite
生成 WCF 客户端类后，您可以创建 WCF 客户端 （实例） 并调用其方法来使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。  
  
 若要创建 WCF 客户端，必须指定一个终结点地址和绑定。 终结点地址必须包含有效的 Oracle E-business Suite 连接 URI，并且该绑定必须为 Oracle E-business Suite 绑定的一个实例 (**OracleEBSBinding**)。 有关 Oracle E-business Suite 连接 URI 的详细信息，请参阅[创建与 Oracle E-business Suite 的连接](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-connection-to-oracle-e-business-suite.md)。 我们建议您不要连接 URI 的一部分指定用户凭据。 您可能会改用**ClientCredentials**的 WCF 客户端，如本主题中所述的属性。  
  
 在代码中或在配置文件中，可以指定 Oracle E-business Suite 绑定和终结点地址。 当你使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]生成 WCF 客户端类，创建配置文件 (app.config) 还为你的项目。 此文件包含反映的绑定属性和连接信息 （除了凭据） 时连接到 Oracle E-business Suite 使用指定的配置设置[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
## <a name="specifying-the-binding-and-endpoint-address-in-code"></a>在代码中指定的绑定和终结点地址  
 下面的代码演示如何通过在代码中使用指定的绑定和终结点地址创建 WCF 客户端**ClientCredentials**的 WCF 客户端的属性。  
  
```  
//Create an Oracle EBS binding and set the binding properties  
OracleEBSBinding binding = new OracleEBSBinding();  
binding.OracleUserName = "myOracleEBSUser";  
binding.OraclePassword = "myOracleEBSPassword";  
binding.OracleEBSResponsibilityName = "Responsibility";  
binding.OracleEBSOrganizationId = "204";  
  
//Create the client endpoint   
EndpointAddress address = new EndpointAddress("oracleebs://<oracleebs_instance_name>/");  
  
//Create the client and specify the credentials  
ConcurrentPrograms_ARClient client = new ConcurrentPrograms_ARClient(binding,address);  
client.ClientCredentials.UserName.UserName = "myuser";  
client.ClientCredentials.UserName.Password = "mypassword";  
  
//Open the client  
client.Open();  
```  
  
## <a name="specifying-the-binding-and-endpoint-address-in-a-configuration-file"></a>在配置文件中指定的绑定和终结点地址  
 下面的代码演示如何通过在 app.config 文件中指定的绑定和终结点地址创建 WCF 客户端。  
  
```  
//Create the client by specifying the endpoint name in the app.config. In this case, the binding properties  
//must also be specified in the app.config.  
ConcurrentPrograms_ARClient client = new ConcurrentPrograms_ARClient("OracleEBSBinding_ConcurrentPrograms_AR");  
  
//Specify the credentials   
client.ClientCredentials.UserName.UserName = "myuser";  
client.ClientCredentials.UserName.Password = "mypassword";  
  
client.Open();  
```  
  
 以下 XML 显示了为创建的配置文件**的客户界面**由并发程序[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 此文件包含在前面的示例中引用的客户端终结点配置。  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<configuration xmlns="http://schemas.microsoft.com/.NetConfiguration/v2.0">  
    <system.serviceModel>  
        <bindings>  
            <oracleEBSBinding>  
                <binding openTimeout="00:05:00" name="OracleEBSBinding" closeTimeout="00:01:00"  
                    receiveTimeout="00:10:00" sendTimeout="00:01:00" clientCredentialType="Database"  
                    inboundOperationType="Polling" metadataPooling="true" statementCachePurge="false"  
                    statementCacheSize="10" pollWhileDataFound="false" pollingInterval="30"  
                    useOracleConnectionPool="true" minPoolSize="1" maxPoolSize="100"  
                    incrPoolSize="5" decrPoolSize="1" connectionLifetime="0" acceptCredentialsInUri="false"  
                    useAmbientTransaction="true" notifyOnListenerStart="true"  
                    notificationPort="-1" dataFetchSize="65536" longDatatypeColumnSize="32512"  
                    skipNilNodes="true" maxOutputAssociativeArrayElements="32"  
                    enableSafeTyping="false" insertBatchSize="20" useSchemaInNameSpace="true"  
                    enableBizTalkCompatibilityMode="true">  
                    <mlsSettings language="" dateFormat="" dateLanguage="" numericCharacters=""  
                        sort="" territory="" comparison="" currency="" dualCurrency=""  
                        iSOCurrency="" calendar="" lengthSemantics="" nCharConversionException="true"  
                        timeStampFormat="" timeStampTZFormat="" timeZone="" />  
                </binding>  
            </oracleEBSBinding>  
        </bindings>  
        <client>  
            <endpoint address="oracleebs://ebs-70-12/" binding="oracleEBSBinding"  
                bindingConfiguration="OracleEBSBinding" contract="ConcurrentPrograms_AR"  
                name="OracleEBSBinding_ConcurrentPrograms_AR" />  
        </client>  
    </system.serviceModel>  
</configuration>  
```  
  
 如果一个项目具有多个 WCF 客户端，将有多个客户端配置文件中定义的终结点条目。 每个 WCF 客户端条目将具有基于其绑定配置和目标 Oracle E-business Suite 项目的唯一名称。 如果连接多个要在项目中创建 WCF 客户端的时间，多个绑定配置条目将创建，另一个用于每个连接。 将按以下方式命名这些绑定配置条目：OracleEBSBinding、 OracleEBSBinding1，等等。 在特定的连接过程中创建每个客户端终结点条目将引用在该连接过程中创建的绑定项。  
  
## <a name="see-also"></a>请参阅  
 [开发 Oracle E-business Suite 应用程序使用 WCF 服务模型](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)