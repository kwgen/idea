title: spring定时调度的注解配置
date: 2016-07-23
---
	@Component
	@Configurable
	@EnableScheduling
	public class TaskScheduler {

		@Autowired
		MtService mtService;
		
		@Scheduled(cron = "0 0 1 * * ?") // 每天1am
		public void clearCommunity() {
			this.mtService.clearCommunity();
		}
		
	}
以注解的形式实现定时调度
