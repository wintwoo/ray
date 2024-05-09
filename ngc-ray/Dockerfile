FROM rayproject/ngc-ray-deps:nightly 

ARG WHEEL_PATH
ARG FIND_LINKS_PATH=".whl"
ARG CONSTRAINTS_FILE="requirements_compiled.txt"

COPY requirements_compiled.txt ./
COPY $WHEEL_PATH .
# COPY $FIND_LINKS_PATH $FIND_LINKS_PATH

RUN pip --no-cache-dir install -c $CONSTRAINTS_FILE \
    `basename $WHEEL_PATH`[all] \
    && sudo rm `basename $WHEEL_PATH`

RUN pip freeze > /home/ray/pip-freeze.txt
