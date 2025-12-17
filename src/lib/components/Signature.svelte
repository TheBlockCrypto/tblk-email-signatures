<script lang="ts">
	export let name = 'Josh Gragg';
	export let title = 'Head of Design';
	export let number = '412-320-9999';
	export let location = 'Colorado Springs, CO (MDT)';
	export let personalTwitter = '';
	export let personalTelegram = '';

	export let twitter = 'https://twitter.com/TheBlock__';
	export let linkedin = 'https://linkedin.com/theblockcrypto/';
	export let telegram = 'https://t.me/theblock';
	export let youtube = 'https://www.youtube.com/@theblockcrypto';

	$: totalBottomPadding = '4px';

	import SocialIcon from '$lib/components/Social.svelte';
</script>

<table
	id="zs-output-sig"
	border="0"
	cellpadding="0"
	cellspacing="0"
	style="font-family:Arial,Helvetica,sans-serif;line-height:0px;font-size:1px;padding:0px!important;border-spacing:0px;margin:0px;border-collapse:collapse; width:500px;"
>
	<tbody>
		<tr>
			<td style="padding:0px!important;">
				<table
					id="inner-table"
					border="0"
					cellpadding="0"
					cellspacing="0"
					style="font-family:Arial,Helvetica,sans-serif;line-height:0px;font-size:1px;padding:0px!important;border-spacing:0px;margin:0px;border-collapse:collapse;"
				>
					<tbody>
						<tr>
							<td height="80" style="display: inline-block; padding: 0 20px;">
								<table
									border="0"
									cellpadding="0"
									cellspacing="0"
									style="font-family:Arial,Helvetica,sans-serif;line-height:0px;font-size:1px;padding:0px!important;border-spacing:0px;margin:0px;border-collapse:collapse;"
								>
									<tbody>
										<tr>
											<td style="border-collapse: collapse; line-height: 0px; padding-right: 1px;">
												<a href="https://www.theblock.co" target="_blank"
													><img
														width="60"
														alt="image"
														border="0"
														src="https://www.tbstat.com/wp/uploads/2025/12/block_logo.png"
													/></a
												>
											</td>
										</tr>
									</tbody>
								</table>
							</td>
							<td
								style="border-collapse:collapse;background-color:#cccccc;width:1px;vertical-align:super;padding:0px!important;"
							/>
							<td style="border-collapse:collapse;padding-right:20px;" />
							<td style="padding:0px!important;">
								<table
									border="0"
									cellpadding="0"
									cellspacing="0"
									style="font-family:Arial,Helvetica,sans-serif;line-height:0px;font-size:1px;padding:0px!important;border-spacing:0px;margin:0px;border-collapse:collapse;"
								>
									<tbody>
										<tr>
											<td
												style="border-collapse:collapse;font-family: Helvetica, sans-serif;font-size:30.0px;font-style:normal;line-height:32px;font-weight:700;padding:0px!important;"
											>
												<span
													style="font-family: Helvetica, sans-serif;font-size:20.0px;font-style:normal;line-height:28px;font-weight:700;color:#111111;display:inline;"
													>{name}</span
												>
											</td>
										</tr>
										<tr>
											<td
												style="border-collapse: collapse; font-family:Helvetica, sans-serif; font-size: 18px; font-style: normal; line-height: 20px; font-weight: 700; padding-bottom: 4px;"
											>
												<span
													style="font-family:Helvetica, sans-serif;font-size:16px;font-style:normal;line-height:20px;font-weight:700;color:#111111;display:inline;"
													>{title}
												</span>
											</td>
										</tr>
										{#if number}
											<tr>
												<td
													style="border-collapse: collapse; font-family:Helvetica, sans-serif; font-size: 12px; font-style: normal; line-height: 14px; font-weight: 400; padding-bottom: 2px;"
												>
													<span
														style="font-family:Helvetica, sans-serif;font-size:12px;font-style:normal;line-height:16px;font-weight:400;color:#111111;display:inline;"
														>{number}</span
													>
												</td>
											</tr>
										{/if}
										<tr>
											<td
												style="border-collapse: collapse; font-family:Helvetica, sans-serif; font-size: 12px; font-style: normal; line-height: 14px; font-weight: 400; padding-bottom: {personalTwitter ||
												personalTelegram
													? '4px'
													: totalBottomPadding}"
											>
												<span
													style="font-family:Helvetica, sans-serif;font-size:12px;font-style:normal;line-height:16px;font-weight:400;color:#111111;display:inline;"
													>{location}</span
												>
											</td>
										</tr>
										{#if personalTwitter}
											<tr>
												<td
													style="border-collapse: collapse; font-family:Helvetica, sans-serif; font-size: 12px; font-style: normal; line-height: 14px; font-weight: 400; padding-bottom: {personalTelegram
														? '4px'
														: totalBottomPadding}"
												>
													<span
														style="font-family:Helvetica, sans-serif;font-size:12px;font-style:normal;line-height:16px;font-weight:400;color:#111111;display:inline;"
														>{personalTwitter}</span
													>
												</td>
											</tr>
										{/if}
										{#if personalTelegram}
											<tr>
												<td
													style="border-collapse: collapse; font-family:Helvetica, sans-serif; font-size: 12px; font-style: normal; line-height: 14px; font-weight: 400; padding-bottom: {totalBottomPadding}"
												>
													<span
														style="font-family:Helvetica, sans-serif;font-size:12px;font-style:normal;line-height:16px;font-weight:400;color:#111111;display:inline;"
														>{personalTelegram}</span
													>
												</td>
											</tr>
										{/if}
										<tr>
											<td
												style="border-collapse: collapse; font-family:Helvetica, sans-serif; font-size: 12px; font-style: normal; line-height: 14px; font-weight: 400; padding-bottom: {totalBottomPadding}"
											>
												<a
													style="font-family:Helvetica, sans-serif;font-size:12px;font-style:normal;line-height:16px;font-weight:400;color:#0B50CF;display:inline;"
													href="https://www.theblock.co"
													target="_blank"
												>
													The Block
												</a>
											</td>
										</tr>
									</tbody>
								</table>
								<table
									border="0"
									cellpadding="0"
									cellspacing="0"
									style="font-family:Arial,Helvetica,sans-serif;line-height:0px;font-size:1px;padding:0px!important;margin: 12px 0 0 0!important;border-spacing:0px;border-collapse:collapse;"
								>
									<tbody>
										<tr>
											<SocialIcon
												logo={'https://www.tbstat.com/wp/uploads/2025/12/xtwitter2.png'}
												url={twitter}
												alt={'twitter'}
											/>
											<SocialIcon
												logo={'https://www.tbstat.com/wp/uploads/2023/05/linkedin-1.png'}
												url={linkedin}
												alt={'linkedin'}
											/>
											<SocialIcon
												logo={'https://www.tbstat.com/wp/uploads/2023/05/telegram-1.png'}
												url={telegram}
												alt={'telegram'}
											/>
											<SocialIcon
												logo={'https://www.tbstat.com/wp/uploads/2025/12/youtube.png'}
												url={youtube}
												alt={'youtube'}
											/>
											<td style="padding:0px!important;" />
										</tr>
										<tr>
											<td style="border-collapse:collapse;padding-bottom:12px;" />
										</tr>
									</tbody>
								</table>
							</td>
						</tr>
					</tbody>
				</table>
			</td>
		</tr>
		<tr>
			<td style="border-collapse:collapse;padding-bottom:16px;"><span /></td>
		</tr>
		​
	</tbody>
</table>
