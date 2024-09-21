修改自：

https://github.com/projectdiscovery


- 修改中国cdn 检测
- 优先中国dns 
- 支持mysql导出
```
./naabu -host target.com -db 'root:password@tcp(192.168.1.x:3306)/scans'
```
```sql
CREATE TABLE `port_scan_results` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `domain` text CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci,
  `ip` varchar(45) NOT NULL,
  `port` int(11) NOT NULL,
  `protocol` varchar(10) ,
  `tls` varchar(10),
  `cdn` varchar(5),           
  `cdn_name` text CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci,
  `time` TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  PRIMARY KEY (`id`)
);
```