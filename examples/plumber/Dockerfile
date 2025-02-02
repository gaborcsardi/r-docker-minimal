FROM rhub/r-minimal

RUN installr -d \
    -t "libsodium-dev curl-dev linux-headers icu-dev" \
    -a "libsodium icu-libs"\
    plumber Rcppcore/Rcpp

WORKDIR /app

COPY . .

EXPOSE 8000

ENTRYPOINT ["R", "-e", "pr <- plumber::plumb('plumber.R'); pr$run(host = '0.0.0.0', port = 8000)"]
