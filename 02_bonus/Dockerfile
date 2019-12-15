FROM alpine:latest
EXPOSE 22
ENTRYPOINT ["/bin/entrypoint"]
ADD sshd_config /etc/ssh/sshd_config
ADD entrypoint.sh /bin/entrypoint
RUN apk add --update --no-cache openssh tmux curl
RUN ssh-keygen -A
RUN adduser -D -s /bin/ash pair
RUN echo "pair:$(date +%s)" | chpasswd
RUN mkdir /home/pair/.ssh && touch /home/pair/.ssh/authorized_keys
RUN chown -R pair:pair /home/pair
