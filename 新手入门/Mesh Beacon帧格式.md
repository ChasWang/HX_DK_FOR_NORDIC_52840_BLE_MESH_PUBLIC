<!--
 * @Description: In User Settings Edit
 * @Author: ��ʱ��
 * @Date: 2019-08-17 13:34:18
 * @LastEditTime: 2019-12-05 21:39:37
 * @LastEditors: Please set LastEditors
 -->
# ǰ��
����ƪ���Ѿ�������ɣ��Ҽ��Ŵ��Ӧ�ö�SIG Mesh�Ѿ����˴�ŵĸ���������������Ǽ���ǰ�����ε��˽���Щ��������α����ʵ�п����������ţ��������ܼ�⵽��Mesh�ű�����ô���ġ�
# SIG Mesh Beacon�غɰ�
��ע��������Mesh�̵̳����ѣ������Ŵ��Ӧ�ö�**SIG MESHЭ������������**���ᵽ��SIG Mesh�غɰ�����ӡ��ɣ�Mesh�����ݰ���BLE�㲥��������һ�����֣�������֡��ʽ����һ�¡���ô����������ʲô�����أ�����ͼ��ʾ��
![](https://github.com/xiaolongba/HX_DK_FOR_NORDIC_52840_BLE_MESH_PUBLIC/blob/master/Material%20library/Mesh_Beacon_Data.png)

����ͼ��֪����ʵMesh Beacon��֡��ʽ���ǱȽϼ򵥵ġ���������С���������**�����**��һ��һ�����������ÿһ���ֶζ��Ǹ�ʲô�ģ���ʲô���ã��������������������[�����--����γ��](https://music.163.com/#/mv?id=5441126)���׸��ٿ���ƪ���£�Ч������:smile:��Ϊ���ô�ҵ���ⲻ�����ڴ������У��˴�С��ֱ�Ӳ�����ʵ��ʾ�����������ʽ�ؽ������յ����ݰ��ǳ�ʲô���ġ���������Ч������ѵģ�**��ʱ����Ҳ��ר�ſ�����Ƶ���⣬�����ڴ�������<---�˴������**���������������´�ʱ����ؿ������������ߣ�
- nRF52840DK���ߺ������ߵĿ�����
- light_switch_server��ʾ������
- SEGGER Embedded Studio

��������ʾ�����̱�������֮�����ǾͿ��Կ���Mesh Beacon���ݰ��ˣ����������ʾ��������ʹ����proxy���ԣ�����ʵ���ϻ������ֲ�ͬ���͵Ĺ㲥����һ����**�������ӷǶ���㲥**������һ����**�����ӷǶ���㲥**����Ȼ��ǰ��������Mesh beacon��������������proxy������صĹ㲥������������ǰ��˳����37��38��39�����㲥�ŵ��ֱ�����Ӧ�����ݰ���**ע�⣺���ﻹ���б�Ҫ��һ�£�MESH�����е��������ݴ��Ͷ���ͨ���������ӷǶ���㲥�����ͳ�ȥ��**���������������ǿ����ڿ��д�����Mesh Beacon��Щʲô���ݣ�

- Unprovisioned Mesh Beacon

  ![](https://github.com/xiaolongba/HX_DK_FOR_NORDIC_52840_BLE_MESH_PUBLIC/blob/master/Material%20library/mesh_beacon_header.png)
  ![](https://github.com/xiaolongba/HX_DK_FOR_NORDIC_52840_BLE_MESH_PUBLIC/blob/master/Material%20library/mesh_beacon_data_payload.png)

- Secure Network Beacon

  ![](https://github.com/xiaolongba/HX_DK_FOR_NORDIC_52840_BLE_MESH_PUBLIC/blob/master/Material%20library/Secure_Network_Beacon.png)

�������ץ���Ľ�ͼ�����ǿ��Կ�����֡��ʽ���Ƿ�ͼ��������һһ��Ӧ�ġ�
## Unprovisioned Mesh Beacon
### Len
����ֶε���˼��˵���mesh beacon����Ч���ݵĳ��ȴ�С **(������Len�ֶ�ռ�õĳ���)**,Ҳ����˵������ץ��ͼ������mesh beacon�ĳ�����25�ֽڣ�**Len�ֶ�**ռ��һ���ֽڣ���ô**Len�ֶ�**�ͱ�ʾ����������Ч���ݵĳ��ȣ��������ͨ�Ĺ㲥����һģһ������·����Ȼ����Ҳ�Ƿǳ�������������Ϊ��mesh��������������BLE�Ĺ㲥���������ݴ��͡�
![](https://github.com/xiaolongba/HX_DK_FOR_NORDIC_52840_BLE_MESH_PUBLIC/blob/master/Material%20library/mesh_beacon_valid_data.png)

### Type
���ֶ�������������ܱߵ��豸˵������һ��Mesh Beacon���ݰ����б���������ͨ��BLE�㲥����

- 0x29

    ��ʾ�����PB-ADV�������ͣ������ڲ��ù㲥����ʱ����Generic Provisioning PDU
- 0x2A

    ��ʾ�����Mesh-Message�������ͣ���������֮��������ݽ��������ݸ�ʽ
- 0x2B
    
    ��ʾ�����Mesh Beacon��������
- 0x01
    
    ��ʾ�����һ����ͨ��BLE�㲥��

���ԣ�������һ���յ��ù㲥��������ʱ�Ϳ���ͨ��������ֶΣ��б���Mesh Beacon������ͨ��BLE�㲥����

### Beacon Type
����������������ǰ���豸�Ƿ��Ѿ������Mesh���磺

- 0x00

    ��ʾ��ǰ���豸����unprovisioned״̬,�ȴ�������Ӧ��mesh���磬��**Unprovisioned Device beacon**
- 0x01

    ��ʾ��ǰ���豸�Ѿ�������mesh���磬��**Secure Network beacon**

- 0x02-0xFF

    �����Χ��ֵ�����������Ժ�ʹ��

### Device UUID
���ֶ�ͨ�׵���˵����ʾÿ���豸��Ψһ��ʶ��(128 bit)����Ҳ���Լ򵥵����Ϊ�豸�����֤���롣�������Ӧ�ò���û���˵�����ǲ��ع��ڹ�ע����������ɵġ���Ϊ���豸���̻������صı�׼ȥ������ЩUUID���Ӷ�����ر�֤UUID��Ψһ�ԡ��������Ȥ�����ѣ����Ե��[������](https://tools.ietf.org/html/rfc4122#section-4.2)��ȡ�������Ϣ��

### OOB Information
���ȣ�ӳ����������**OOB**������ʡ��ҹ����кܶ���߿���������ʵĵ�һ��Ӧ���� **��What the hell?��**��
![](https://github.com/xiaolongba/HX_DK_FOR_NORDIC_52840_BLE_MESH_PUBLIC/blob/master/Material%20library/what.gif)

OOB��ȫ����**Out of Band��Ҳ���Ǵ������ݵ���˼**����ʵ˵���˾��ǲ����뵱ǰ��ʹ�õķ�ʽ��ͬ�ķ�ʽȥ�������ݣ���NFC�������롢��ά��ȵȡ����ǣ�ǰ���Ǹ��豸����߱����������� **(�е�������BLE�����ʱ��IO Capabilities)**�������㽫����Ҫ���ø��ֶε����ݡ�Ŀǰ��Mesh Spec v1.0.1֧�ֵ�OOB Information������ʾ��

| Bit | Description |
|-----|-----|
| 0 | Other    |
| 1 | Electronic / URI    |
| 2 | 2D machine-readable code    |
| 3 | Bar code    |
| 4 | Near Field Communication (NFC)    |
| 5 | Number    |
| 6 | String    |
| 7 | Reserved for Future Use    |
| 8 | Reserved for Future Use    |
| 9 | Reserved for Future Use    |
| 10 | Reserved for Future Use    |
| 11 | On box    |
| 12 | Inside box    |
| 13 | On piece of paper    |
| 14 | Inside manual    |
| 15 | On device    |

��ô������ֶ��Ǹ�ʲô�õ��أ���Ҫ���������������������Ĺ��� **(�������ת���豸�Ĺ�Կ)**

### URI Hash
�����һ����ѡ���ֶΣ�Ҳ����˵���ǿ��п��޵ġ�����Ҫ���Ǹ���provisioner��ǰ�����õ��豸��ʲô���͵Ķ���������֮���ƺ�Ҳû��̫������á���ֵ����������ļ��㹫ʽ���ã�
> URI Hash = s1(URI Data)[0-3]
## Secure Mesh Network Beacon
### Len
�˴������ظ����������������**Unprovisioned Mesh Beacon**��**Len**�½ڼ��ɡ�

### Type
�˴������ظ����������������**Unprovisioned Mesh Beacon**��**Type**�½ڼ��ɡ�

### Beacon Type
�˴������ظ����������������**Unprovisioned Mesh Beacon**��**Beacon Type**�½ڼ��ɡ�

### Flags
���ֶ���Ҫ����**Key Refresh Flag**��**IV Update Flag**��������:

| Bits | Definition |
|-----|-----|
| 0 | Key Refresh Flag (0: False 1: True)    |
| 1 | IV Update Flag (0: Normal operation  1: IV Update active)    |
| 2�C7 | Reserved for Future Use     |

����Ҫ�����þ������ڸ����ܱߵ��豸����Ҫ׼������NetKey��AppKey����IV Index�����ˣ�һ���������֮����Ӧ�ı�־λ�ͻᱻ��0��

### Network ID
����˼���������ID�ţ�Ҳ����˵��ǰSecure Network Beacon�������Mesh�����ID�ţ����IDһ���ǲ����ģ�������������µ�����һ���������NetKey�����˲Ż�����

### IV Index
ͬ���ģ����ֶα�ʾ���mesh���統ǰ��IV�����š�ΪʲôҪ˵�ǵ�ǰ���أ���������IV Index�ǿ��Ը��µġ���ô��IV Index����ʲô�����أ�

1. ����Ӧ�ò�������������֤�ͼ���
2. ��**Sequence Number**��Ҫ���ʱ������**IV Update**������**IV Index**ֵ���ӣ��Ӷ���ֹ**Sequence Number**���ظ�ʹ��

### Authentication Value 
���һ���ֶΣ������ʾ�֪���϶����Ǹ�������صġ���ֵ��ͨ�����µĹ�ʽ������ģ�

> Authentication Value = AES-CMAC <sub>BeaconKey</sub> (Flags || Network ID || IV Index) [0�C7]

����**BeaconKey**���������ģ����ǲ��ع���׷�����޷Ǿ��Ǵ�NetKey���������ģ�ͨ��һϵ�еĹ�ʽ�㷨��������ġ�
```c
salt = s1(��nkbk��)
P = ��id128�� || 0x01
BeaconKey = k1 (NetKey, salt, P) 
```
����ж���ϣ�����ε��˽�,�����Ķ�Mesh Spec v1.0.1�ĵ�**3.8.6.3.4**�½ڡ�ͬ���ģ�Network IDҲ�Ǵ�NetKey�������� **(�����Ķ�Mesh Spec v1.0.1�ĵ�3.8.6.3.2�½�)** ��
> Network ID  = k3 (NetKey)

�ܶ���֮��һ��NetKeyֻ������һ��**BeaconKey**��**Network ID**,�Ӷ�Ҳ��˵ֻ������һ��**Authentication Value**��

